<script>
    import EmbeddedBlock from '$lib/components/EmbeddedBlock.svelte';
    import EmbeddedBlockText from '$lib/components/EmbeddedBlockText.svelte';
    import { base } from '$app/paths';
</script>


<div class="content_container">
    <div class="main_image">
        <img class="top_image" alt="Оптический телеграф" src="{base}/images/a/telegraph.png">
    </div>
    <ul>
        <li class="part_name">
            <p>Оптический телеграф</p>
        </li>
        <li class="part_text">
            <p>
                В XVIII веке передача информации на большие расстояния была крайне медленной и сложной. Каждое улучшение в способах передачи сигналов воспринималось как значительный шаг вперед, поскольку потребность в оперативной связи становилась всё более острой. Особенно в ней нуждались правительства европейских государств, ведущих многочисленные войны, где скорость передачи приказов и сообщений между армиями могла решить исход сражений.
                <br><br>
                Единственным доступным решением этой проблемы были оптические телеграфы. Эти системы позволяли передавать условные сигналы — буквы, слоги или слова — с помощью семафорных устройств. Станции, расположенные на расстоянии прямой видимости друг от друга, образовывали цепочку, по которой информация могла быстро перемещаться между пунктами отправления и получения.
                <br><br>
                Кулибин разработал свою собственную оригинальную конструкцию оптического телеграфа, взяв за основу принцип сигнализации, предложенный французским изобретателем Шаппом. Однако русский механик существенно усовершенствовал систему. Для составления телеграфных знаков он использовал конструкцию из трёх крыльев: одного длинного и двух коротких.
                <br><br>
                Кроме того, он  разработал собственный секретный телеграфный код, который стал важным шагом в упрощении передачи информации. В отличие от кода Шаппа, содержавшего 9460 знаков, система Кулибина включала всего 235. Слова передавались по частям, разделяясь на однозначные и двузначные слоги, а код был сведён к одной таблице, занимая промежуточное положение между алфавитным и цифровым методами.
                <br><br>
                Несмотря на наличие детально разработанного Кулибиным проекта телеграфа, никто в царской России им не заинтересовался. Проект был сдан в архив. Впервые телеграф поставили в России только через 40 лет — в 1835 году, причем установка его была проведена сотрудником Шаппа, инженером Шато. Правительство заплатило Шато 120 тысяч рублей за секрет телеграфа и 6 тысяч годовой пожизненной пенсии. И это при наличии более совершенного проекта Кулибина, никем даже не рассмотренного.
            </p>
        </li>
        <li>
            <h2 class="subtitle">Код для оптического телеграфа</h2>
            <img src="{base}/images/a/telegraph_code.png" alt="Код для оптического телеграфа">
        </li>

    </ul>


</div>


<style>
    :root {
        --top-image-margin: 50%;
    }
    li {
        padding-top: 10px;
    }
    .part_name p {
        font-weight: 700;
        font-size: 34pt;
        line-height: 120%;
        letter-spacing: -2%;
        text-align: center;
        color: #000957;
    }
    .part_text p {
        line-height: 140%;
        letter-spacing: 0%;
    }

    .content_container {
        justify-content: center;
        height: 100%;
        background-color: #fff4f4;
        padding: 0 20px;
        overflow: hidden;
    }

    .main_image {
        width: 100%;
        height: auto;
        padding-top: 20px;
        margin: 0;
    }

    .top_image {
        width: 551px;
        margin: 0 auto;
    }

    .subtitle {
        margin: 0 0 0.5rem 0;
        font-size: 1.25rem;
        font-weight: 600;
        color: #1f2937;
    }

    @media (max-width: 551px) {
        .content_container {
            padding: 0 20px;
        }

        .top_image {
            width: calc(100% + var(--top-image-margin));
            max-width: none;
            margin: 0 calc(-1*(var(--top-image-margin)/2));
        }
    }

</style>
