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
        width: 172.5px;
        height: 40px;
        gap: 8px;
        border-radius: 100px;
        border-width: 1px;
        color: #344CB7;
        border: 1px solid #344CB7
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
        transition: opacity 0.5s
        cursor: not-allowed;
        pointer-events: none;
    }
    

</style>


