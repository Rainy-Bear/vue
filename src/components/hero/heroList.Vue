<template>
  <div class="container">
    <lol-header></lol-header>
    <hero-list-con></hero-list-con>
    <lol-bottom></lol-bottom>
  </div>
</template>

<script>
  import LolHeader from '../header/lolHeader.vue';
  import HeroListCon from './heroListCon.vue';
  import LolBottom from '../bottom/lolBottom.vue';

  export default {
    components: {
      LolHeader,
      HeroListCon,
      LolBottom
    },
    name: 'lol'
  };
</script>
