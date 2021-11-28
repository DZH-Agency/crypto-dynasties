<template>
  <div id="app">
    <common-navbar/>
    <div class="content">
<!--      <common-header/>-->
<!--      <young-crypto/>-->
<!--      <show-case/>-->
<!--      <our-mission/>-->
      <artist-section/>
    </div>
  </div>
</template>

<script>

import CommonNavbar from "@/components/CommonNavbar";
import CommonHeader from "@/components/CommonHeader";
import YoungCrypto from "@/components/YoungCrypto";
import ShowCase from "@/components/ShowCase";
import OurMission from "@/components/OurMission";
import ArtistSection from "@/components/ArtistSection";
export default {
  name: 'App',
  components: {
    ArtistSection,
    OurMission,
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
