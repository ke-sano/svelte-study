<script>
  export let images;

  let centerIndex = 0;
  $: leftIndex =  (centerIndex - 1 + images.length) % images.length;
  $: rightIndex =  (centerIndex + 1) % images.length;

  function sliderMoveLeft() {
    centerIndex = (centerIndex - 1 + images.length) % images.length;
  }

  function sliderMoveRight() {
    centerIndex = (centerIndex + 1 + images.length) % images.length;
  }
</script>

<template lang="pug">
.slider
    img.slider-item.left(src="{images[leftIndex]}" alt="スライダー画像(左)")
    img.slider-item(src="{images[centerIndex]}" alt="スライダー画像")
    img.slider-item.right(src="{images[rightIndex]}" alt="スライダー画像(右)")
    button.slider-left-button(on:click!="{sliderMoveLeft}") ←
    button.slider-right-button(on:click!="{sliderMoveRight}") →
</template>

<style lang="stylus">
  .slider
    position relative
    width 80%
    margin 0 10%
    .slider-item
      width 100%
      &.left
        position absolute
        top 0
        right 100%
      &.right
        position absolute
        top 0
        left 100%
    .slider-left-button
        position absolute
        top 50%
        right 100%
    .slider-right-button
        position absolute
        top 50%
        left 100%
</style>