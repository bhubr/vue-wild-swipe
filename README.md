# Vue Simple Swipe

> :trophy: All credits go to Ana Tudor for her post on [CSS Tricks](https://css-tricks.com/): [Simple Swipe with Vanilla JavaScript](https://css-tricks.com/simple-swipe-with-vanilla-javascript/)

This is a simple swipe component for Vue.js. Online demo [here](https://bhubr.github.io/vue-wild-swipe-example/).

## What's here

* [Caveats](#install)
* [Install](#install)
* [Example](#example)
* [Props](#props)
* [Changelog](#changelog)

## Caveats

As I'm rather new to Vue, and don't know (yet) how to package icons along with the JS component, you need to add a CSS file and a `fonts` folder to your project.

You can find them in the `src/styles` folder of this repo, or from the [example's repo](https://github.com/bhubr/vue-wild-swipe-example/tree/master/src/styles).

Just import the `icons.css` file from your main component, as shown [here](https://github.com/bhubr/vue-wild-swipe-example/blob/master/src/App.vue#L44)

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

## Props

The component accepts the following props:

* `images`: an array of image URLs (required)
* `arrows`: a boolean indicating whether to show the previous & next arrows (optional, default `true`)
* `bullets`: a boolean indicating whether to show bullets beneath the images (optional, default `true`)
* `keys`: a boolean indicating if left & right directions should show the previous & next image (optional, default `true`)

## Changelog

* 0.9.1 First working version
* 0.9.2 Add example to readme
* 0.9.3 Add arrows, bullets, key controls
* 0.9.4 Improve readme (document props, caveats, reference online demo)
