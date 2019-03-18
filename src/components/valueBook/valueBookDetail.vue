<template>
  <div class="container">
    <lol-header></lol-header>
    <value-book-detail-con></value-book-detail-con>
    <lol-bottom></lol-bottom>
  </div>
</template>

<script>
  import LolHeader from '../header/lolHeader.vue';
  import ValueBookDetailCon from './valueBookDetailCon.vue';
  import LolBottom from '../bottom/lolBottom.vue';

  export default {
    components: {
      LolHeader,
      ValueBookDetailCon,
      LolBottom
    },
    name: 'lol'
  };
</script>
