<script>
    import EmbeddedBlock from '$lib/components/EmbeddedBlock.svelte';
    import EmbeddedBlockText from '$lib/components/EmbeddedBlockText.svelte';
</script>

<link href="https://fonts.googleapis.com/css2?family=Inter:wght@400;700&display=swap" rel="stylesheet">


<div class="content-container">
    <div class="compare-text-container">
        <div class="compare-text">
            Сравнение с другими изобретениями
        </div>
    </div>  

    
    <div class="slider-container">
        <div class="slider">
            SLIDER
        </div>
    </div>
    
    <div class="heading-container">
        <div class="heading">
            Самокатка
        </div>
    </div> 

    <ul class="content-list">
        <li class="text">
            <p>
                Самокатка или же коляска, приводимая в действие силами человека, не была новым изобретением. Подобные устройства существовали еще в эпоху Возрождения. В России до Кулибина ее создал нижегородский крестьянин Шамшуренков. Однако Кулибин, не знакомый с этими проектами, считал свое устройство оригинальным. 
            </p>
        </li>
        <li class="text">
            <p>
                Одновременно изобретатель разрабатывал четырехколесную и трехколесную самокатку, однако современники рассказывают лишь о второй. Принцип ее работы был достаточно прост: при поочередном нажатии ногами на “туфли” (так Кулибин называл педали) посредством присоединенных тяг их качательное движение переводилось во вращение оси тележки. Инерция установленного махового колеса придавала ходу равномерность. Торможение же осуществлялось с помощью натянутых часовых пружин, которые разжимались в нужный момент. Такая система тормоза была инновационной по сравнению с самокатками, созданными до Кулибина. Однако у нее был один большой минус: останавливаться на высокой скорости было невозможно, так как это могло грозить поломкой зубцов. Для уменьшения трения использовалось что-то похожее на современные подшипники (такая же система использовалась в подъемнике Кулибина). Согласно расчетам изобретателя, устройство было способно достичь скорости в 30 км/ч (что, конечно, очень сомнительно: такая скорость была бы очень высокой).
            </p>
        </li>
        <!-- <li class="text">
            <p></p>
        </li> -->
        <li class="text">
            <p>
                К сожалению, Кулибин по тем или иным причинам уничтожил почти все чертежи этого изобретения, из-за чего многие его подробности нам неизвестны (например, как работало рулевое управление). Возможно, он посчитал, что подобное устройство - всего лишь забава, возможно, хотел разрушить свой образ “придворного механика”, ведь идея самокатки могла заинтересовать только привилегированные слои общества.
            </p>
        </li>
        <li class="text">
            <p>
                После Великой французской революции похожее устройство появилось во Франции, только управлял им не слуга, а сам человек. “Бегунки” (именно так они назывались) впоследствии эволюционировали в современный велосипед.
            </p>
        </li>
        <li class="fact">
            <EmbeddedBlock title="Любопытный факт">
                <EmbeddedBlockText slot="full">
                    В 1693 г. некий европейский изобретатель Ришар создал самокатку, механизм которой был на удивление схож с механизмом самокатки Кулибина (рычаги, педали, храповое колесо). Так, два изобретателя создали практически одинаковые механизмы, при этом не зная друг друга.
                </EmbeddedBlockText>
            </EmbeddedBlock>
        </li>
    </ul>
</div>


<style>
    :root {
        --primary-color: #000957;
        --heading-color: #000000;
        --secondary-color: #344CB7;
        --nav-color: #FFF2F2;
        --secondary-hover-color: #FFAE00;
        --nav-font-size-for-pc: 32px;
        --nav-font-size-for-phone: 29px;
        --font-heading-size-for-small-devices: 32px;
        --font-heading-size: 48px;
        --nav-element-height: 62px;
        --test-bg-color-1: rgba(255, 150, 150, 0.5);
        --test-bg-color-2: rgba(150, 150, 255, 0.5);
        --test-font-size: 100px;
    }
    
    .content-container {
        position: absolute;
        top: 80px;
    }

    .slider-container {
        height: 531px;
        margin-left: 16px;
        margin-right: 16px;
        margin-top: 16px;
        text-align: center;
        display: flex;
        align-items: center;
        justify-content: center;
        background-color: var(--test-bg-color-1);
    }

    .slider {
        font-size: 48px;
        font-weight: 700;
        font-family: Inter;
        color: var(--primary-color);
    }

    .compare-text-container {
        min-width: 0;
        width: calc(100% - 32px);
        /* background-color: var(--test-bg-color-1); */
        margin-left: 16px;
        margin-right: 16px;
        display: flex;
        justify-content: center;
        text-align: center;
        align-items: center;
    }

    .compare-text {
        font-family: Inter;
        font-weight: 400;
        color: var(--primary-color);
        font-size: 32px;
    }

    .text {
        margin-top: 20px;
        margin-left: 16px;
        margin-right: 16px;
    }

    .text p {
        font-family: Inter;
        font-weight: 400;
        font-size: 16px;
    }

    * {
        margin: 0;
        padding: 0;
        box-sizing: border-box;
        font-family: inherit;
    }
    .heading {
        margin-top: 16px;
        font-family: Inter;
        font-weight: bold;
        font-size: 48px;
        color: var(--primary-color);
    }

    .fact {
        margin-left: 16px;
        margin-right: 16px;
    }

    .heading-container {
        width: 100%;
        /* background-color: var(--test-bg-color-1); */
        display: flex;
        align-items: center;
        justify-content: center;
    }

    @media screen and (max-width: 300px) {
        .heading {
            font-size: 32px;
        }

        .text {
            margin-top: 15px;
        }
    }

    @media screen and (max-width: 380px) {
        .compare-text {
            font-size: 26px;
        }
    }

</style>