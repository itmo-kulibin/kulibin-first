<script>
  import EmbeddedBlock from '$lib/components/EmbeddedBlock.svelte';
  import EmbeddedBlockText from '$lib/components/EmbeddedBlockText.svelte';
</script>

<EmbeddedBlock title="Любопытный факт">
  <EmbeddedBlockText slot="short">
    В 1772 году Лондонская академия назначила большую премию тому, кто сделает лучшую модель...
  </EmbeddedBlockText>
  <EmbeddedBlockText slot="full">
    В 1772 году Лондонская академия назначила большую премию тому, кто сделает лучшую модель одновременного моста, без свай, концы которого упирались бы только на берегах реки. Модель Кулибина полностью соответствовала требованиям, однако он отказался посылать проект в Англию, ведь очень хотел построить мост именно в России, на Неве, а не на Темзе.
  </EmbeddedBlockText>
</EmbeddedBlock>

<EmbeddedBlock>
  <EmbeddedBlockText slot="short">
    "...Мешает правильному ходу 
    То, что употребив свободу..."
  </EmbeddedBlockText>
  <EmbeddedBlockText slot="full">
    "...Мешает правильному ходу  
    То, что употребив свободу,  
    Стремится слабый человек  
    Замедлить мира плавный бег..."  

    И. П. Кулибин "В ознаменование  
    Светлого Господнего воскресения  
    1764 г"
  </EmbeddedBlockText>
</EmbeddedBlock>
