<script>
import Vue from 'vue';
import VueSimpleSwipe from '@/vue-simple-swipe.vue';

export default Vue.extend({
  name: 'ServeDev',
  components: {
    VueSimpleSwipe
  }
});
</script>

<template>
  <div id="app">
    <vue-simple-swipe />
  </div>
</template>
