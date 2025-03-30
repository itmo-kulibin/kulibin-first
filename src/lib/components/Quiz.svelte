<script>
    import QuizAnswer from './QuizAnswer.svelte';
    const defaultData = {
        question: "Вопрос викторины ?",
        answers : [
            {answer: "Ответ А", correct : true},
            {answer: "Ответ Б", correct : false},
            {answer: "Ответ В", correct : false},
            {answer: "Ответ Г", correct : false},
        ]
    };
    let active = $state(null);
    let { data = defaultData } = $props();
</script>


<div class="QuizBlock">
    <p class="text-4xl font-bold">{ data.question }</p>
    <div class="button-container">    
        <div class="buttons">
            {#each data.answers as answer, index}
                <QuizAnswer 
                answer={answer.answer} 
                correct={answer.correct}
                active={active === null || active === index}
                setIndex={() => active = index}
                />  
            {/each} 
        </div>    
    </div>
</div>

<style>
    .QuizBlock {
        width: min(357px, 100%);
        display: flex;
        flex-direction: column;
        align-items: center;
        justify-content: center;
        /* height: 164px;     */
        gap: 12px;
    }
    p {
        position: relative;
        font-size: 18pt;
        color: #2D336B;
        line-height: 120%;
        letter-spacing: -2%;
        margin-bottom: 12px;
        
    }
    .button-container {
    }

    .buttons {
        position: relative;
        display: grid;
        grid-template-columns: repeat(2, minmax(0, 1fr));
        gap: 12px;
        align-items: stretch;
    }

    @media screen and (max-width: 800px) {
        p {
            font-size: 15pt;
        }
    }
    
</style>
