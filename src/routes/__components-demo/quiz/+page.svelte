<script>
    import QuizAnswer from '$lib/components/QuizAnswer.svelte';
    import Quiz from '$lib/components/Quiz.svelte';
    const data = {
        question: "Так кто такой Кулибин ?",
        answers : [
            {answer: "Изобретатель", correct : true},
            {answer: "Историк", correct : false},
            {answer: "Путешественник", correct : false},
            {answer: "Клименков", correct : false}
        ]
    };
</script>

<div class="demo">
<Quiz {data} />

<Quiz />
</div>
<style>
    .demo {
        background-color: #fff4f4;
        height: 100vh; 
    }
</style>