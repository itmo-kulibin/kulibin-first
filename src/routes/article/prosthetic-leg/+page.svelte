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
            Слайдер
        </div>
    </div>

    <div class="heading-container">
        <div class="heading">
            Протез("механическая нога")
        </div>
    </div> 

    <ul class="content-page">
        <li class="text">
            <p>
                Во время русско-турецкой войны 1787–1791 годов, при штурме очаковской крепости (1788 г.), поручик артиллерии Непейцын потерял ногу выше колена. Познакомившись с Кулибиным, он попросил его смастерить для него искусственную ногу.
            </p>
        </li>
        <li class="text">
            <p>
                В 1791 г. протез был готов. Механическая нога была сделана из металла, обложена пробкой и обшита замшей. Она имела форму человеческой ноги и сгибалась, как настоящая. Протез был полым внутри для лёгкости. Изделие прикреплялось к туловищу с помощью пластины, оканчивающейся подмышкой, подобно костылю, и ремней. Человек опирался одновременно и на ногу, и на костыль. Вся конструкция пряталась под одеждой.
            </p>
        </li>
        <li class="text">
            <p>
                В результате протез стал настолько удобным, что Непейцыну не пришлось ходить с тростью или костылём, и он даже мог танцевать. Затем в светском обществе люди не могли понять, откуда у Непейцына «выросла» нога. А сам Непейцын благодаря протезу успешно продолжил военную карьеру и смог дослужиться до чина полковника, а после – генерал-майора.
            </p>
        </li>
        <li class="text">
            <p>
                Кулибин же в 1808 году сделал ещё несколько механических ног с их чертежами и описаниями, например:
            </p>
        </li>
        <img src="/static/Image/prosthetic-leg.png" alt="Механическая нога" class="image">
        <img src="/static/Image/prosthetic-leg_1.png" alt="Механическая нога" class="image">
        <li class="text">
            <p>
                Помимо самих ног, Кулибин изготовил две куклы для наглядной демонстрации своих протезов. Первая кукла изображала человека, потерявшего ногу выше колена, а вторая – ниже колена. Кстати, всё это он делал за свой счёт и сам платил мастерам, участвовавшим в создании кукол (резному мастеру, живописцу, портному, парикмахеру, сапожнику).
            </p>
        </li>
        <li class="text">
            <p>
                Как отметил известный тогда профессор хирургии Иван Буш, Кулибинский протез стал первым протезом, на который опиралось всё туловище, что позволяло не доставлять изделию дискомфорт больному. Он признал протез самым совершенным из всех имеющихся в то время протезов.
            </p>
        </li>
        <li class="interesting_fact">
            <EmbeddedBlock title="Любопытный факт">
                <EmbeddedBlockText slot="short">
                    Некий французский подданый спустя несколько лет вывез одну из моделей кулибинских протезов во Францию и представил её самому Наполеону, выдав за своё изобретение. В результате он был награждён крупной суммой денег, и запустил в производство эти протезы для снабжения ими французской армии.
                </EmbeddedBlockText>
            </EmbeddedBlock>
        </li>
    </ul>
</div>


<style>
    .image {
        position: relative;
        width: 600px;
        height: 400px;
        overflow: hidden;
        margin: 0 auto 30px auto;
    }

    .content-container {
        position: absolute;
        top: 80px;
    }

    .slider-container {
        text-align: center;
    }

    .compare-text-container {
        min-width: 0;
        width: calc(100% - 32px);
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
        color:#000957;
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
        color: #000957;
    }
    .interesting_fact {
        margin-left: 16px;
        margin-right: 16px;
    }
    .heading-container {
        width: 100%;
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