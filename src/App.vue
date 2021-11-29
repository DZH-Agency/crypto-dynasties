<template>
  <div id="app">
    <common-navbar/>
    <div class="content">
      <common-header :timer-data="timerData"/>
      <div id="story">
        <young-crypto/>
      </div>
      <div id="about">
        <show-case/>
      </div>
<!--      <our-mission/>-->
<!--      <div id="artist">-->
<!--        <artist-section/>-->
<!--      </div>-->
<!--      <div id="faq">-->
<!--        <questions-section/>-->
<!--      </div>-->
<!--      <dont-miss :timer-data="timerData"/>-->
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
  },
  data() {
    return {
      timerData: {
        days: '00',
        hours: '00',
        minutes: '00',
        seconds: '00'
      },
      targetDate: new Date(2021, 11, 20, 0, 0, 0, 0),
      diffInSeconds: null
    }
  },
  mounted() {
    setInterval(() => {
      this.diffInSeconds = Math.floor(Math.abs(this.targetDate - new Date()) / 1000);

      const days = Math.floor(this.diffInSeconds / 86400);
      this.diffInSeconds -= days * 86400;

      // calculate hours
      const hours = Math.floor(this.diffInSeconds / 3600) % 24;
      this.diffInSeconds -= hours * 3600;

      // calculate minutes
      const minutes = Math.floor(this.diffInSeconds / 60) % 60;
      this.diffInSeconds -= minutes * 60;

      this.timerData = {
        days: String(days).padStart(2, '0'),
        hours: String(hours).padStart(2, '0'),
        minutes: String(minutes).padStart(2, '0'),
        seconds: String(this.diffInSeconds).padStart(2, '0')
      }

    }, 1000)
  }
}
</script>

<style lang="scss">
@import "~@/assets/scss/main.scss";
</style>
