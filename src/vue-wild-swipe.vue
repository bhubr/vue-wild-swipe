<script>
import VanillaSwipe from "./vanilla-swipe";

export default {
  name: "VueWildSwipe", // vue component name
  props: ["images"],
  watch: {
    images: function (newImages, oldImages) {
      if (newImages && (newImages !== oldImages) && newImages.length > 0) {
        this.swiper.refreshNumImages(newImages.length);
      }
    },
  },
  mounted() {
    this.swiper = new VanillaSwipe(this.$refs.container);
  },
  beforeDestroy() {
    this.swiper.unbindEventListeners();
  },
};
</script>

<template>
  <div class="vue-wild-swipe">
    <div class="container" ref="container">
      <img :src="url" v-for="url in images" :key="url" />
    </div>
  </div>
</template>

<style scoped>
.vue-wild-swipe {
  max-width: 100%;
  overflow-x: hidden;
  height: 100%;
}

.container {
  --n: 1;
  display: flex;
  align-items: center;
  overflow-y: hidden;
  width: 100%;
  height: 100%;
  width: calc(var(--n) * 100%);
  max-height: 100vh;
  transform: translate(calc(var(--i, 0) / var(--n) * -100%));
}

.container img {
  width: 100%;
  width: calc(100% / var(--n));
  user-select: none;
  pointer-events: none;
}
</style>
