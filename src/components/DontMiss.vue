<template>
  <div class="miss-wrapper">
    <div class="container">
      <div class="miss">
        <div class="miss-counter-wrapper">
          <div class="miss-counter">
            <h3 class="miss-counter__heading">
              Don't Miss Your Chance To Own The World's First On-Chain Crypto Mascot...
            </h3>
            <div class="miss-counter-time">
              <span data-time="Days">{{ timerData.days }}</span>:<span data-time="Hours">{{ timerData.hours }}</span>:<span data-time="Minutes">{{ timerData.minutes }}</span>:<span data-time="Seconds">{{ timerData.seconds }}</span>
            </div>
            <div class="miss-counter__exclusively">
              Exclusively on
              <a href="#">
                <img src="@/assets/img/CommonHeader/crypto-com.png" alt="crypto-com">
              </a>
            </div>
            <div class="miss-counter__btn">
              <span>View Drop</span>
              <div class="bg"></div>
            </div>
          </div>
        </div>

      </div>
    </div>
  </div>
</template>

<script>
export default {
  props: {
    timerData: {
      type: Object,
      required: true
    }
  },
  name: "DontMiss"
}
</script>

<style scoped lang="scss">
@import "~@/assets/scss/components/DontMiss.scss";
</style>