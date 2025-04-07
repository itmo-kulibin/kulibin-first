<script>
    import EmbeddedBlock from '$lib/components/EmbeddedBlock.svelte';
    import EmbeddedBlockText from '$lib/components/EmbeddedBlockText.svelte';
</script>

<link href="https://fonts.googleapis.com/css2?family=Inter:wght@400;700&display=swap" rel="stylesheet">


<div class="content-container">
    <div class="heading-container">
        <div class="heading">
            <h2> Протез("механическая нога")</h2>
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
                В результате протез стал настолько удобным, что Непейцыну не пришлось ходить с тростью или костылём, и он даже мог танцевать. Затем в светском обществе люди не могли понять, откуда у Непейцына «выросла» нога. А сам Непейцын благодаря протезу успешно продолжил военную карьеру и смог дослужиться до чина полковника, а после — генерал–майора.
            </p>
        </li>
        <li class="text">
            <p>
                Кулибин же в 1808 году сделал ещё несколько механических ног с их чертежами и описаниями, например:
            </p>
        </li>

        <div class="split-image">
            <img src="/images/a/pleg-1.png" alt="Механическая нога">
            <img src="/images/a/pleg-2.png" alt="Механическая нога">
        </div>
        <div class="split-image">
            <img src="/images/a/pleg-4.png" alt="Механическая нога">
            <img src="/images/a/pleg-3.png" alt="Механическая нога">
        </div>

        <li class="text">
            <p>
                Помимо самих ног, Кулибин изготовил две куклы для наглядной демонстрации своих протезов. Первая кукла изображала человека, потерявшего ногу выше колена, а вторая — ниже колена. Всё это он делал за свой счёт и сам платил мастерам, участвовавшим в создании кукол (резному мастеру, живописцу, портному, парикмахеру, сапожнику).
            </p>
        </li>
        <li class="text">
            <p>
                Как отметил известный тогда профессор хирургии Иван Буш, Кулибинский протез стал первым протезом, на который опиралось всё туловище, что позволяло не доставлять изделию дискомфорт больному. Он признал изобретение самым совершенным из всех имеющихся в то время протезов.
            </p>
        </li>
        <li class="interesting_fact">
            <EmbeddedBlock title="Любопытный факт">
                <EmbeddedBlockText slot="full">
                    Согласно некоторым свидетельствам, одна из моделей кулибинского протеза была вывезена во Францию и представлена самому Наполеону, который запустил ее в производство для снабжения протезами французской армии.
                </EmbeddedBlockText>
            </EmbeddedBlock>
        </li>
    </ul>
</div>


<style>
    .split-image {
        display: flex;
        justify-content: center;
        margin: 10px auto;
    }
    .split-image img {
        max-height: 250px;
    }

    .image {
        //margin: 0 auto 30px auto;
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
        font-weight: bold;
        font-size: 48px;
        color: #000957;
        text-align: center;
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
    @media screen and (max-width: 500px) {
        .heading {
            font-size: 24px;
        }
        .text {
            margin-top: 15px;
        }
        .compare-text {
            font-size: 26px
        }
    }

    @media screen and (max-width: 360px) {
        .heading {
            font-size: 20px;
        }
    }
</style>
