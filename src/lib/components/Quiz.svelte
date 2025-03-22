<script>
    import QuizAnswer from './QuizAnswer.svelte';
    const defaultData = {
        question: "Вопрос викторины ?",
        answers : [
            {answer: "Ответ А", correct : true},
            {answer: "Ответ Б", correct : false},
            {answer: "Ответ В", correct : false},
            {answer: "Ответ Г", correct : false}
        ]
    };
    let { data = defaultData } = $props();
</script>


<div class="QuizBlock">
    <p>{ data.question }</p>
    <div class="buttons">
        {#each data.answers as answer}
            <QuizAnswer answer={answer.answer} correct={answer.correct} />  
        {/each}
    </div>    
</div>

<style>
    .QuizBlock {
        width: 357px;
        height: 164px;    
        gap: 12px;
    }
    p {
        font-size: 18pt;
        color: #2D336B;
        line-height: 120%;
        letter-spacing: -2%;
        margin-bottom: 12px;
    }
    .buttons {
        display: grid;
        grid-template-columns: repeat(2, 1fr);
        gap: 12px;
    }
</style>