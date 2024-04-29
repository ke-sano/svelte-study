<script>
  import Slider from './Slider.svelte';

  let cart = [];

  function addToCard(productId) {
    cart = [...cart, productId];
  }

  let product = {
    id: 'svelte-book',
    name: 'Svelte Book',
    price: 3500,
    images: [
      'https://github.com/svelte-book/sample-app/raw/main/static/svelte-book-1.png',
      'https://github.com/svelte-book/sample-app/raw/main/static/svelte-book-2.png',
      'https://github.com/svelte-book/sample-app/raw/main/static/svelte-book-3.png',
    ],
  };

  let relatedProducts = [
    {
      id: 'react-book',
      name: 'React Book',
      price: 3500,
    },
    {
      id: 'vue-book',
      name: 'Vue Book',
      price: 3500,
    },
    {
      id: 'angular-book',
      name: 'Angular Book',
      price: 3500,
    },
  ];
</script>

<template lang="pug">
  header.header
    a.header-title(href="/") Svelte EC
    nav
      ul.header-links
        li ようこそゲストさん
        li
          a(href="/cart") カート
  
  article.product
    .product-main
      .image-container
        Slider(images!="{product.images}")
      div
        h2 {product.name}
        dl
          dt 価格
          dd {product.price}
        div
          +if("!cart.includes(product.id)")
            button(on:click!="{() => addToCard(product.id)}") カートに入れる
            +else()
              button(disabled) カートに追加済み

    footer
      h3 関連商品
      ul
        +each("relatedProducts as product")
          li
            a(href="/products/{product.id}") {product.name}
            | &nbsp;- {product.price}円
</template>

<style lang="stylus">
  :global(body)
    margin 0
    background-color #eee
    padding 0
  
  .header
    display flex
    justify-content space-between
    align-items center
    margin 0 auto
    background-color #fff
    padding 0 15px
    width 100%
    max-width 800px
    height 50px
    .header-title
      font-weight bold
    .header-links
      display flex
      gap 10px
      margin 0
      padding 0
      list-style none
  .product
    margin 0 auto
    background-color #fff
    padding 15px
    width 100%
    max-width 800px
    .product-main
      display flex
      flex-wrap wrap
      gap 20px
      .image-container
        width 100%
        max-width 400px
        overflow hidden
        img
          width 100%
</style>
