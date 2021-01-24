<script>
export default {
  name: 'VueSimpleSwipe', // vue component name
  props: ['images'],
  watch: {
    images: function(newImages, oldImages) {
      console.log('Prop changed: ', newImages, ' | was: ', oldImages)
    }
  }
};
</script>

<template>
  <div class="vue-simple-swipe">

  </div>
</template>

<style scoped>

</style>
