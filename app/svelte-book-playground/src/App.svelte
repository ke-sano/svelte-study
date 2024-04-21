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
        img(
          src="https://github.com/svelte-book/sample-app/raw/main/static/svelte-book-1.png"
          alt="「Svelte Guide」表紙"
        )

  div
    h2 Svelete Guide
    dl
      dt 価格
      dd 3500円
    div
      button カートに入れる

  footer
    h3 関連商品
    ul
      li
        a(href="/product/react-book") React Book
      li
        a(href="/product/vue-book") Vue Book
      li
        a(href="/product/angular-book") Angular Book
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
    padding 0
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
