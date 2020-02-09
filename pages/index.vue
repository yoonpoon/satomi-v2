<template>
  <section class="has-bg">
    <Nav />
    <div
      :style="{ backgroundImage: 'url(' + imgUrl + ')' }"
      class="container bg-img"
    ></div>
  </section>
</template>

<script>
import Nav from '@/components/global/Nav'
export default {
  components: {
    Nav
  },
  data() {
    return {
      imgUrl:
        'https://www.thesun.co.uk/wp-content/uploads/2016/11/nintchdbpict000281024550.jpg?w=4000'
    }
  }
}
</script>

<style lang="scss">
.container {
  margin: 0 auto;
  min-height: 100vh;
  display: flex;
  justify-content: center;
  align-items: center;
  text-align: center;
  &.bg-img {
    background-position: 50% 50%;
    background-size: contain;
    height: 100vh;
    background-attachment: scroll;
    @media only screen and (max-width: 912px) {
      background-size: cover;
    }
  }
}
</style>
