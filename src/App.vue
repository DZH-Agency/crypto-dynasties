<template>
  <div id="app">
    <common-navbar ref="navbar"/>
    <div class="content" ref="content">
      <common-header/>
    </div>
  </div>
</template>

<script>

import CommonNavbar from "@/components/CommonNavbar";
import CommonHeader from "@/components/CommonHeader";
export default {
  name: 'App',
  components: {
    CommonHeader,
    CommonNavbar
  },
  mounted() {
    this.$refs.content.style.marginTop = this.$refs.navbar.$el.clientHeight + 'px';
  }
}
</script>

<style lang="scss">
@import "~@/assets/scss/main.scss";
</style>
