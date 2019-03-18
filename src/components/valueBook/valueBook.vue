<template>
  <div class="container">
    <lol-header></lol-header>
    <value-book-con></value-book-con>
    <lol-bottom></lol-bottom>
  </div>
</template>

<script>
  import LolHeader from '../header/lolHeader.vue';
  import ValueBookCon from './valueBookCon.vue';
  import LolBottom from '../bottom/lolBottom.vue';

  export default {
    components: {
      LolHeader,
      ValueBookCon,
      LolBottom
    },
    name: 'lol'
  };
</script>
