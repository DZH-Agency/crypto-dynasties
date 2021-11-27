<template>
  <div id="app">
    <common-navbar ref="navbar"/>
    <div class="content">

    </div>
  </div>
</template>

<script>

import CommonNavbar from "@/components/CommonNavbar";
export default {
  name: 'App',
  components: {
    CommonNavbar
  }
}
</script>

<style lang="scss">
@import "~@/assets/scss/main.scss";
</style>
