<script>
    let showSidebar = false;
    import BiographyPoint from '$lib/components/BiographyPoint.svelte';
    import QuizAnswer from '$lib/components/QuizAnswer.svelte';
    import Quiz from '$lib/components/Quiz.svelte';

    let data = [
        {
            question: "Как назывался журнал, который выпускала Екатерина II?",
            answers : [
                {answer: "Северная пчела", correct : false},
                {answer: "Всякая всячина", correct : true},
                {answer: "Куранты", correct : false},
                {answer: "Утренние часы", correct : false}
            ]
        },
        {
            question: "Как звали мужа Екатерины II, свергнув которого, она стала императрицей?",
            answers : [
                {answer: "Павел I", correct : false},
                {answer: "Петр II", correct : false},
                {answer: "Петр III", correct : true},
                {answer: "Иван VI", correct : false}
            ]
        },
        {
            question: "Где хранятся кулибинские часы в форме яйца?",
            answers : [
                {answer: "Русский музей", correct : false},
                {answer: "Лувр", correct : false},
                {answer: "Эрмитаж", correct : true},
                {answer: "Академия наук", correct : false}
            ]
        },
        {
            question: "Какие знаменитые часы, сейчас выставленные в Эрмитаже, собирал и ремонтировал Кулибин?",
            answers : [
                {answer: "Феникс", correct : false},
                {answer: "Фазан", correct : false},
                {answer: "Рябчик", correct : false},
                {answer: "Павлин", correct : true}
            ]
        },
        {
            question: "Как звали английского механика, создавшего часы «Павлин»?",
            answers : [
                {answer: "Иоганн Бернулли", correct : false},
                {answer: "Джеймс Кокс", correct : true},
                {answer: "Жан Леон д’Аламбер", correct : false},
                {answer: "Жан Франсуа Бэкар", correct : false}
            ]
        },
        {
            question: "Кто подписал указ об учреждении Академии Наук, механиком которой служил Кулибин?",
            answers : [
                {answer: "Алексей Михайлович", correct : false},
                {answer: "Петр I", correct : true},
                {answer: "Елизавета Петровна", correct : false},
                {answer: "Екатерина II", correct : false}
            ]
        },
        {
            question: "Откуда родом была императрица Екатерина II?",
            answers : [
                {answer: "Франция", correct : false},
                {answer: "Австрия", correct : false},
                {answer: "Германия", correct : true},
                {answer: "Россия", correct : false}
            ]
        },
        {
            question: "Что не относится к правлению Павла I?",
            answers : [
                {answer: "Объявление себя магистром католического Мальтийского ордена", correct : false},
                {answer: "Разрешение телесных наказаний для дворян", correct : false},
                {answer: "Введение ассигнаций", correct : true},
                {answer: "Организация Индийского похода", correct : false}
            ]
        },
    ];


</script>

<link href="https://fonts.googleapis.com/css2?family=Inter:wght@400;700&display=swap" rel="stylesheet">

<div class="content__container">
    <ul>
        <li><p class="heading">
            Детство и юность
        </p></li>
        <li><div class="bio-node">
            <BiographyPoint year=1735>
                <div class="bio-text-container">
                    <p class="bio-text-text">Иван Петрович Кулибин родился 10 (21) апреля 1735 года в селе Подновье Нижегородского уезда в семье зажиточного торговца мукой. Его отец, Пётр Иванович Кулибин, был старообрядцем, придерживался традиционных устоев и ожидал того же от своей семьи. Все дети воспитывались в строгости и с ранних лет были приучены к труду.</p>
                    <p class="bio-text-text">Пётр Иванович не счёл нужным отправить сына в школу, поручив его обучение местному дьяку. Иван быстро освоил грамоту, и вскоре начал помогать отцу за прилавком. Однако торговля его не привлекала — куда больше его интересовали чтение книг и создание разных механизмов. Ещё в детстве он смастерил из дерева маленькую, но сложную модель мукомольной мельницы с вращающимися жерновами, используя обычный карманный нож.</p>
                    <p class="bio-text-text">Отец, однако, не одобрял этих занятий, находя их лишь напрасной тратой времени. Он с досадой ломал искусно выполненные Иваном изделия, запрещая ему прикасаться к инструментам. Видя в сыне будущего купца, продолжателя своего дела, он не мог разглядеть пользы в этих детских поделках и всячески старался искоренить это увлечение.</p>
                </div>
            </BiographyPoint>
        </div></li>
        <li><div class="bio-node">
            <BiographyPoint year=1748>
                <div class="bio-text-container">
                    <p class="bio-text-text">Его отношение изменилось, когда в 13 лет будущий изобретатель построил настоящую небольшую гидросистему — с помощью системы шлюзов бесполезный «мёртвый» пруд превратился в водоём со свежей водой, в котором прекрасно себя чувствовала рыба. Поражённый, Пётр Иванович был вынужден признать практичность занятий сына. Это был настоящий маленький триумф, и Иван с удвоенными усилиями стал изучать слесарное, токарное и часовое дело.</p>
                    <p class="bio-text-text">Особенное впечатление на него произвели часы на колокольне Строгановской (Рождественской) церкви в Нижнем Новгороде. Помимо времени, по ним можно было узнать изменение лунных фаз и движение солнца. При этом вращался сам циферблат, а не стрелка, и ежечасно площадь вокруг наполнялась проигрываемой музыкой. Эти часы были одной из самых сложных и искусных работ, доступных для наблюдения во всём Нижегородском уезде. По одной из легенд, будучи пятнадцатилетним подростком, Кулибин участвовал в процессе их восстановления.</p>
                    <p class="bio-text-text">Важно отметить, что в XVIII веке механические часы были не просто предметом интерьера, а настоящим чудом техники, доступным лишь избранным. Каждый экземпляр был изготовлен на заказ, а создание точных внутренних механизмов было одной из наиболее сложных инженерных задач. Помимо этого, часы олицетворяли собой принцип автоматизации как таковой и несли в себе сильный философский посыл. Потому значительная часть изобретателей, механиков и инженеров XVIII века по совместительству являлись часовщиками.</p>
                    <p class="bio-text-text">Иван Петрович Кулибин не был исключением. Он стремился понять принципы работы часовых механизмов. У Кулибина не было ни инструментов, ни знаний, подобные тонкие устройства были редкостью, а во всём Нижнем Новгороде не было ни одного часовых дел мастера.</p>
                    <p class="bio-text-text">После долгих поисков и уговоров Иван смог изучить устройство часов с кукушкой, принадлежащих одному из богатых купцов. Однако, без специальных инструментов и наставника его мечта создать собственные часы казалась недостижимой.</p>
                </div>
            </BiographyPoint>
        </div></li>
        <li>
            <div class="question">
                <Quiz data={data[0]}/>
            </div>
        </li>
        <li><div class="bio-node">
            <BiographyPoint year=1754>
                <div class="bio-text-container">
                    <p class="bio-text-text">Шанс представился в 1754 году, когда 19–летний Кулибин отправился с отцом в Москву по торговым делам. В Москве он познакомился с мастером-часовщиком Лобковым, который не только показал ему инструменты своего ремесла, но и объяснил, как с ними работать.</p>
                    <p class="bio-text-text">Иван сумел уговорить мастера продать ему старый сломанный набор инструментов. Вернувшись домой, Кулибин самостоятельно починил их, и с невероятным энтузиазмом взялся за работу. Уже через несколько месяцев его усилия увенчались успехом — он создал свои первые деревянные часы с кукушкой.</p>
                    <p class="bio-text-text">Так в Нижнем Новгороде появился первый часовых дел мастер.</p>
                </div>
            </BiographyPoint>
        </div></li>
        <li><p class="heading">
            Становление
        </p></li>
        <li><div class="bio-node">
            <BiographyPoint year=1758>
                <div class="bio-text-container">
                    <p class="bio-text-text">В 1758 году, после смерти отца, 23–летний Кулибин открыл небольшую мастерскую, где изготавливал и чинил часы. Слухи о его таланте быстро разнеслись по городу, и вскоре к нему обратился губернатор со сложным заказом. Иван блестяще справился с задачей, что ещё больше укрепило его репутацию. Теперь заказы от богатых горожан стали поступать к нему регулярно.</p>
                </div>
            </BiographyPoint>
        </div></li>
        <li>
            <div class="question">
                <Quiz data={data[5]}/>
            </div>
        </li>
        <li><div class="bio-node">
            <BiographyPoint year=1764>
                <div class="bio-text-container">
                    <p class="bio-text-text">В 1764 году императрица Екатерина II посетила Нижний Новгород. Кулибин решил воспользоваться этим шансом и создать нечто невероятное. Заручившись поддержкой своего друга и покровителя богатого купца Костромина, с 1764 по 1767 год он трудился над уникальным подарком, который должен был поразить императрицу.</p>
                    <p class="bio-text-text">Этот невероятный механизм, выполненный в форме гусиного яйца, состоял из 427 крошечных деталей и был не просто часами, а целым миниатюрным театром–автоматом. Каждый час в нём разыгрывались целые мистерии: внутри механизма находились движущиеся фигурки, показывавшие библейские сюжеты, а мелодичный звон сопровождал смену сцен.</p>
                    <p class="bio-text-text">Уникальный подарок привёл Екатерину II в полный восторг. Восхищённая талантом мастера, она предложила ему возглавить механические мастерские при Академии наук в Санкт–Петербурге.</p>
                </div>
            </BiographyPoint>
        </div></li>
        <li>
            <div class="question">
                <Quiz data={data[1]}/>
            </div>
        </li>
        <li><p class="heading">
            Жизнь в Петербурге
        </p></li>
        <li><div class="bio-node">
            <BiographyPoint year=1769>
                <div class="bio-text-container">
                    <p class="bio-text-text">27 февраля 1769 года Кулибин прибыл в Санкт–Петербург. Ему выплатили солидную премию, назначили годовое жалование в 350 рублей и предоставили жильё. С головой погрузившись в работу, Иван не переставал учиться, осваивая математику, физику и механику.</p>
                </div>
                <div class="bio-text-container">
                    <p class="bio-text-text">Под его руководством мастерские Академии наук достигли небывалого расцвета. Здесь не только чинили, но и создавали уникальные приборы и механизмы, поражавшие своей сложностью и изяществом. Кулибин превратил мастерские в настоящий центр инженерной мысли.</p>
                </div>
                <div class="bio-text-container">
                    <p class="bio-text-text">В Петербурге чрезвычайно остро стояла проблема сообщения между частями города, разделенными Невой, и Кулибин посвятил немало времени поиску её решения.</p>
                </div>
            </BiographyPoint>
        </div></li>
        <li><div class="bio-node">
            <BiographyPoint year=1772>
                <div class="bio-text-container">
                    <p class="bio-text-text">В 1772 году он представил проект одноарочного моста длиной 298 метров. Модель, выполненная в масштабе 1:10, успешно прошла испытания, однако проект так и не был реализован.</p>
                </div>
            </BiographyPoint>
        </div></li>
        <li>
            <div class="question">
                <Quiz data={data[2]}/>
            </div>
        </li>
        <li><div class="bio-node">
            <BiographyPoint year=1777>
                <div class="bio-text-container">
                    <p class="bio-text-text">В 1777 году князь Григорий Потёмкин приобрёл для Екатерины II часы «Павлин». После перевозки механизм оказался повреждён, и его восстановление поручили Кулибину. Только спустя три недели подготовки он смог приступить к ремонту. Благодаря глубокому знанию европейских механических систем, он вернул часы в рабочее состояние, а впоследствии не раз участвовал в их разборке и сборке. Ему всегда удавалось точно воспроизвести сложные движения деталей и фигурок птиц. Сегодня этот шедевр хранится в Эрмитаже в Санкт–Петербурге и является одним из символов музея.
                </div>
            </BiographyPoint>
        </div></li>
        <li><div class="bio-node">
            <BiographyPoint year=1779>
                <div class="bio-text-container">
                    <p class="bio-text-text">В 1779 году Кулибин удивил современников ещё одним изобретением — фонарём–прожектором. Это устройство, внешне напоминавшее обычный фонарь, внутри скрывало параболический отражатель из множества маленьких зеркал. Оно настолько усиливало свет свечи, что позволяло читать книги на улице даже ночью.</p>
                </div>
            </BiographyPoint>
        </div></li>
        <li><div class="bio-node">
            <BiographyPoint year=1790-e>
                <div class="bio-text-container">
                    <p class="bio-text-text">В 1791 году Кулибин собрал экипаж, ход которому давал человек, крутящий педали, а не привычная упряжка лошадей. Изобретение было оснащено коробкой скоростей, тормозами и маховиком.</p>
                </div>
                <div class="bio-text-container">
                    <p class="bio-text-text">В середине 1790–х годов императрица Екатерина II, испытывая трудности с передвижением по Зимнему дворцу, обратилась к Ивану Кулибину с просьбой создать для неё подъёмное кресло. Задача перед изобретателем стояла не из лёгких. Особенность конструкции заключалась в том, что наверху кресло оставалось открытым, что исключало возможность использования традиционной лебёдки. Крепление же лебёдки снизу создавало бы неудобства для пассажира.</p>
                    <p class="bio-text-text">Кулибин нашёл оригинальное решение: он закрепил основание кресла на длинном винте, по которому оно двигалось наподобие гайки. Екатерина садилась в кресло, слуга вращал рукоять, и винт плавно поднимал её на нужный этаж.</p>
                    <p class="bio-text-text">Этот винтовой лифт был создан в 1793 году, что на несколько десятилетий опередило создание аналогичного механизма Элишей Отисом в Нью-Йорке.</p>
                </div>
            </BiographyPoint>
        </div></li>
        <li>
            <div class="question">
                <Quiz data={data[3]}/>
            </div>
        </li>
        <li><div class="bio-node">
            <BiographyPoint year=1794>
                <div class="bio-text-container">
                    <p class="bio-text-text">В 1794 году Кулибин представил ещё одно опередившее своё время изобретение — оптический телеграф. Это устройство позволяло передавать сигналы на большие расстояния с помощью системы зеркал и световых импульсов. Хотя проект был технически совершенным и многообещающим, он, как и многие другие идеи Кулибина, не получил широкого практического применения.</p>
                </div>
                <div class="bio-text-container">
                    <p class="bio-text-text">Кулибин также внёс значительный вклад в развитие протезирования. Он создал уникальный протез — «механическую ногу» — для поручика Сергея Непейцына, потерявшего конечность при штурме Очакова. Этот протез был настолько удачным, что Непейцын, получивший прозвище «Железная нога», смог остаться на военной службе. Идеи Кулибина позже вдохновили европейских изобретателей и получили развитие во Франции, став важным шагом в истории протезирования.</p>
                </div>
                <div class="bio-text-container">
                    <p class="bio-text-text">Но, несмотря на выдающиеся успехи, жизнь изобретателя нельзя было назвать лёгкой. Немецкая партия академиков, обладавшая значительным влиянием, невзлюбила Кулибина.</p>
                </div>
                <div class="bio-text-container">
                    <p class="bio-text-text">Двор осыпал его милостями, но на деле Иван ощущал отсутствие внимания к своим проектам, что приводило его в отчаяние. Без его участия не обходился ни один придворный праздник, бал или карнавал, его изобретения поражали публику, а их автор не находил финансовой поддержки.</p>
                </div>
            </BiographyPoint>
        </div></li>
        <li><div class="bio-node">
            <BiographyPoint year=1800>
                <div class="bio-text-container">
                    <p class="bio-text-text">В октябре 1800 года Иван Кулибин писал своей дочери, что его обстоятельства «очень неблагоприятны». Так и осталось неизвестным, что это были за «обстоятельства», но 24 августа 1801 года он уволился из Академии наук.</p>
                    <p class="bio-text-text">Александр I закрепил за ним пенсионное жалование в размере его зарплаты, а также выдал денег для погашения долгов, накопившихся при проведении опытов.</p>
                </div>
            </BiographyPoint>
        </div></li>
        <li>
            <div class="question">
                <Quiz data={data[4]}/>
            </div>
        </li>
        <li><p class="heading">
            Возвращение в Нижний Новгород
        </p></li>
        <li><div class="bio-node">
            <BiographyPoint year=1804>
                <div class="bio-text-container">
                    <p class="bio-text-text">Вернувшись в родной город, Иван Петрович, несмотря на преклонный возраст, не оставил своих изысканий. Изобретатель занялся созданием самоходных судов, способных двигаться против течения. В 1804 году он успешно испытал вторую модель водохода, которая показала отличные результаты. Однако проект был отвергнут, и вскоре судно было продано на дрова.</p>
                </div>
                <div class="bio-text-container">
                    <p class="bio-text-text">В своих поздних работах Кулибин экспериментировал с паровыми двигателями, разрабатывал проекты мельниц, машин для добычи соли и даже тайно пытался создать вечный двигатель. Но годы брали своё. Несмотря на всероссийскую известность, к концу жизни Иван Петрович оказался в бедности.</p>
                </div>
            </BiographyPoint>
        </div></li>
        <li><div class="bio-node">
            <BiographyPoint year=1818>
                <div class="bio-text-container">
                    <p class="bio-text-text">30 июля (11 августа) 1818 года великий русский механик скончался. Чтобы оплатить его похороны, жена была вынуждена продать последние оставшиеся в доме часы.</p>
                </div>
                <div class="bio-text-container">
                    <p class="bio-text-text">Так закончился путь одного из величайших русских изобретателей.</p>
                </div>
            </BiographyPoint>
        </div></li>
        <li>
            <div class="question">
                <Quiz data={data[6]}/>
            </div>
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

    * {
        margin: 0;
        padding: 0;
        box-sizing: border-box;
        font-family: inherit;
    }

    .content__container {
        width: 100%;
        position: absolute;
        top: 70px;
        /* padding-top: 60px; */
    }

    .content__container ul {
        width: 100%;
        list-style: none;
        /* background-color: var(--test-bg-color-1); */
        padding-top: 10px;
        padding-bottom: 10px;
    }

    .heading {
        position: inherit;
        width: 60%;
        font-size: var(--font-heading-size);
        font-family: Inter;
        font-weight: bold;
    }

    .question {
        display: flex;
        align-items: center;
        justify-content: center;
        width: calc(100%-64px);
        margin-left: 16px;
        position: relative;
        /* background-color: var(--test-bg-color-2); */
        margin-right: 16px;
        margin-bottom: 10px;
        margin-top: 30px;
    }

    @media screen and (max-width: 800px) {
        .heading {
            font-size: var(--font-heading-size-for-small-devices);
        }
    }

    .bio-text-text {
        margin-bottom: 20px;
    }

    .content__container ul li {
        margin-left: 16px;
        margin-right: 16px;
        margin-bottom: 10px;
        width: calc(100% - 32px);
        /* background-color: var(--test-bg-color-2); */
    }
</style>
