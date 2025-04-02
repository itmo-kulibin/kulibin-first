<script>
    let { answer = "none", correct = false, active = true, setIndex} = $props(); 
    const STATES = { NEUTRAL: 0, CORRECT: 1, INCORRECT: 2 };
    let buttonState = $state(STATES.NEUTRAL);
    function checkTrue() {
        if(correct){
            buttonState = STATES.CORRECT;
        }else{
            buttonState = STATES.INCORRECT;
        }
        setIndex();
    }
</script>

<button class="QuizButton text-lg {buttonState == 0 ? '' : buttonState == 1 ? 'correct' : 'incorrect'} {active ? '' : 'inactive'}" onclick={checkTrue} >
    {answer}
</button>

<style>
    @keyframes revealAnswer {
        from {
            background-color: transparent;
            color: black;
        }
        to {
            background-color: var(--final-color);
            color: white;
        }
    }

    .QuizButton {
        display: flex;
        align-items: center;
        justify-content: center;
        width: min(172.5px, calc(((100vw - 76px) / 2)));
        min-height: 60px;
        font-size: 18px;
        gap: 8px;
        border-radius: 100px;
        border-width: 1px;
        color: #344CB7;
        border: 1px solid #344CB7
    }

    @media screen and (max-width: 340px) {
        .QuizButton {
            font-size: 16px;
            min-height: 40px;
        }
    }

    @media screen and (max-width: 318px) {
        .QuizButton {
            font-size: 12px;
            min-height: 40px;
        }
    }

    .QuizButton:hover {
        border: 1px solid #000957
    }

    .correct {
        --final-color: #4CAF50;
        animation: revealAnswer 0.5s forwards;
    }

    .incorrect {
        --final-color: #FF5722;
        animation: revealAnswer 0.5s forwards;
    }
    .inactive {
        opacity: 0.5;
        transition: opacity 0.5s;
        cursor: not-allowed;
        pointer-events: none;
    }
    

</style>


