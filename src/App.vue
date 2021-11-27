<template>
  <div id="app">
    <common-navbar/>
    <div class="content">
<!--      <common-header/>-->
<!--      <young-crypto/>-->
      <show-case/>
    </div>
  </div>
</template>

<script>

import CommonNavbar from "@/components/CommonNavbar";
import CommonHeader from "@/components/CommonHeader";
import YoungCrypto from "@/components/YoungCrypto";
import ShowCase from "@/components/ShowCase";
export default {
  name: 'App',
  components: {
    ShowCase,
    YoungCrypto,
    CommonHeader,
    CommonNavbar
  }
}
</script>

<style lang="scss">
@import "~@/assets/scss/main.scss";
</style>
