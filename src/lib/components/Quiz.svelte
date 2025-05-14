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
    let selectedIndex = $state(null);
    let { data = defaultData } = $props();
</script>

<div class="QuizBlock">
    <p class="text-4xl font-bold">{ data.question }</p>
    <div class="buttons">
        {#each data.answers as answer, index}
            <QuizAnswer
            answer={answer.answer}
            correct={answer.correct}
            active={selectedIndex === null || selectedIndex === index}
            selectedIndex={selectedIndex}
            index={index}
            setIndex={() => selectedIndex = index}
            />
        {/each}
    </div>
</div>

<style>
    .QuizBlock {
        width: 100%;
        display: flex;
        flex-direction: column;
        align-items: center;
        justify-content: center;
        gap: 12px;
        margin-bottom: 30px;
    }
    p {
        position: relative;
        font-size: 18pt;
        color: #2D336B;
        line-height: 120%;
        margin-bottom: 12px;

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
