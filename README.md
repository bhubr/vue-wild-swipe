# Vue Simple Swipe

> :trophy: All credits go to Ana Tudor for her post on [CSS Tricks](https://css-tricks.com/): [Simple Swipe with Vanilla JavaScript](https://css-tricks.com/simple-swipe-with-vanilla-javascript/)

## Install

```
npm install vue-wild-swipe
```

## Example

```vue
<script>
import Vue from "vue";
import VueWildSwipe from "vue-wild-swipe";

const imageSets = [
  [
    "https://images.unsplash.com/photo-1611514615258-c1d33efb091c?ixid=MXwxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHw%3D&ixlib=rb-1.2.1&auto=format&fit=crop&w=800&q=80",
    "https://images.unsplash.com/photo-1611456645963-149eaae07d47?ixid=MXwxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHw%3D&ixlib=rb-1.2.1&auto=format&fit=crop&w=1350&q=80",
    "https://images.unsplash.com/photo-1611433634706-39c25bb5b39f?ixid=MXwxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHw%3D&ixlib=rb-1.2.1&auto=format&fit=crop&w=634&q=80",
  ],
  [
    "https://images.unsplash.com/photo-1611513418382-7dd6487cc28f?ixid=MXwxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHw%3D&ixlib=rb-1.2.1&auto=format&fit=crop&w=658&q=80",
    "https://images.unsplash.com/photo-1611513160864-03606aae8f8d?ixid=MXwxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHw%3D&ixlib=rb-1.2.1&auto=format&fit=crop&w=1350&q=80",
    "https://images.unsplash.com/photo-1611477408172-216f82fdda49?ixid=MXwxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHw%3D&ixlib=rb-1.2.1&auto=format&fit=crop&w=1352&q=80",
    "https://images.unsplash.com/photo-1611443558105-3031b7fa945d?ixid=MXwxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHw%3D&ixlib=rb-1.2.1&auto=format&fit=crop&w=675&q=80",
  ],
];

export default Vue.extend({
  name: "ServeDev",
  components: {
    VueWildSwipe,
  },
  data: function () {
    return {
      images: imageSets[0],
      setIndex: 0,
      showSwiper: true,
    };
  },
  methods: {
    changeImages() {
      this.setIndex = (this.setIndex + 1) % 2;
      this.images = imageSets[this.setIndex];
    },
    toggleSwiper() {
      this.showSwiper = !this.showSwiper;
    },
  },
});
</script>

<template>
  <div id="app">
    <vue-wild-swipe v-if="showSwiper" :images="images" />

    <div class="controls">
      <button type="button" @click="changeImages">Change images</button>
      <button type="button" @click="toggleSwiper">Toggle swiper</button>
    </div>
  </div>
</template>

<style>
body {
  margin: 0;
}

#app {
  height: 80vh;
}

.controls {
  text-align: center;
}
</style>
```