<template>
  <div id="app">
    <common-navbar/>
    <div class="content">
      <common-header/>
      <young-crypto/>
      <show-case/>
      <our-mission/>
      <artist-section/>
      <questions-section/>
      <dont-miss/>
    </div>
    <common-footer/>
  </div>
</template>

<script>

import CommonNavbar from "@/components/CommonNavbar";
import CommonHeader from "@/components/CommonHeader";
import YoungCrypto from "@/components/YoungCrypto";
import ShowCase from "@/components/ShowCase";
import OurMission from "@/components/OurMission";
import ArtistSection from "@/components/ArtistSection";
import QuestionsSection from "@/components/QuestionsSection";
import DontMiss from "@/components/DontMiss";
import CommonFooter from "@/components/CommonFooter";
export default {
  name: 'App',
  components: {
    CommonFooter,
    DontMiss,
    QuestionsSection,
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
