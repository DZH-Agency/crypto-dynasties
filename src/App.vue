<template>
  <div id="app">
    <common-navbar/>
    <div class="content">
      <common-header :timer-data="timerDate"/>
      <div id="story">
        <young-crypto/>
      </div>
      <div id="about">
        <show-case/>
      </div>
      <div id="utility">
        <our-mission/>
      </div>
      <div id="artist">
        <artist-section/>
      </div>
      <div id="faq">
        <questions-section/>
      </div>
      <dont-miss :timer-data="timerDate"/>
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
  targetDate: null,
  data() {
    return {
      timerDate: {
        days: '00',
        hours: '00',
        minutes: '00',
        seconds: '00'
      },
      diffInSeconds: null
    }
  },
  mounted() {
    // const targetDate = new Date(Date.UTC(2022, 3, 14, 24))
    // targetDate.setHours(targetDate.getHours() - 8 + new Date().getTimezoneOffset() / 60)
    // this.$options.targetDate = targetDate
    //
    // setInterval(() => {
    //   const today = new Date(new Date().getTime() + new Date().getTimezoneOffset() * 60 * 1000 + new Date().getTimezoneOffset() / 60 * 1000)
    //   today.setHours(today.getHours() - 8)
    //
    //   let diffInSeconds = Math.floor((this.$options.targetDate - today) / 1000);
    //   if (diffInSeconds <= 0) {
    //     return
    //   }
    //
    //   const days = Math.floor(diffInSeconds / 86400);
    //   diffInSeconds -= days * 86400;
    //
    //   // calculate hours
    //   const hours = Math.floor(diffInSeconds / 3600) % 24;
    //   diffInSeconds -= hours * 3600;
    //
    //   // calculate minutes
    //   const minutes = Math.floor(diffInSeconds / 60) % 60;
    //   diffInSeconds -= minutes * 60;
    //
    //   this.timerDate = {
    //     days: String(days).padStart(2, '0'),
    //     hours: String(hours).padStart(2, '0'),
    //     minutes: String(minutes).padStart(2, '0'),
    //     seconds: String(diffInSeconds).padStart(2, '0')
    //   }
    //
    // }, 1000)
  }
}
</script>

<style lang="scss">
@import "~@/assets/scss/main.scss";
</style>
