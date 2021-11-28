<template>
  <div class="header-wrapper">
    <div class="container">
      <img src="@/assets/img/CommonHeader/headerCirclesDesktop.png" alt="" class="header__circles-img desktop-only">
      <div class="header">
        <img src="@/assets/img/CommonHeader/Bitcoin.png" alt="btc" class="header__img"/>
        <div class="header-count">
          <div class="header-count__title">
            Industry Renowned NFT Artist Nuxer Unveils World’s First
            Crypto Mascot Collection
          </div>
          <div class="header-count__crypto-text">
            "CryptoDynasties"
          </div>
          <div class="header-count-counter">
            <div class="header-count-counter-time">
              <span data-time="Days">02</span>:<span data-time="Hours">09</span>:<span data-time="Minutes">02</span>:<span data-time="Seconds">02</span>
            </div>
            <div class="header-count-counter__exclusively">
              Exclusively on
              <a href="#">
                <img src="@/assets/img/CommonHeader/crypto-com.png" alt="crypto-com">
              </a>
            </div>
            <div class="header-count-counter__btn">
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
  name: "CommonHeader"
}
</script>

<style scoped lang="sass">
@import "~@/assets/scss/components/CommonHeader.scss"
</style>