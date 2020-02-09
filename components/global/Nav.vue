<template>
  <header class="bg-black-90 fixed w-100 ph3 pv3 pv4-ns ph4-m ph5-l">
    <nav class="f6 fw6 ttu tracked nav">
      <a class="link dim white dib mr3" href="#" title="Home">STATUS BAR</a>
      <a class="link dim white dib" href="#" title="Contact">NAV BAR</a>
    </nav>
  </header>
</template>

<script>
export default {
  name: 'Nav'
}
</script>

<style lang="scss">
.nav {
  width: 100%;
  display: flex;
  justify-content: space-between;
}
</style>
