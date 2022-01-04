<template>
  <div class="sc-wrapper">
    <div class="container">
      <picture>
        <source srcset="@/assets/img/ShowCase/bgCurveLine.png" media="(min-width: 1024px)">
        <img src="@/assets/img/ShowCase/bgCurveMobile.png" alt="bg-img" class="sc__bg-curve-line-img">
      </picture>

      <img src="@/assets/img/ShowCase/bgSliderCurve.png" alt="bg-img" class="sc__bg-slider-curve-img">
      <div class="sc">
        <img src="@/assets/img/ShowCase/bgSmallStar.png" alt="bg-img" class="sc__bg-small-star-img desktop-only">
        <h3 class="sc__title">Inside The DNA Of CryptoDynasties</h3>
        <p class="sc__text">
          CryptoDynasties is a 3D art collection where every attribute was curated and designed with an exceptional
          attention to detail to produce the most unique NFT avatars on the market today. The end result took over two
          months of brainstorming sessions and careful craftsmanship to give form to some of the biggest CryptoDynasties
          leading the revolution today: Bitcoin, Ethereum, Binance Coin, Cardano and Dogecoin.
        </p>
        <div class="sc-images-controls">
          <div class="control-arrow control-arrow_left" ref="prevBaseBtn" :class="{disabled: !allowSlides.prev}"></div>
          <div class="sc-images-controls__name">{{ currentBaseSlidePlatform }}</div>
          <div class="control-arrow control-arrow_right" ref="nextBaseBtn" :class="{disabled: !allowSlides.next}"></div>
        </div>
        <div class="sc-images-wrapper swiper" ref="imagesSwiper">
          <div class="sc-images swiper-wrapper">
            <div class="sc-images-item swiper-slide" v-for="(nft, index) in nfts" :key="index">
              <div class="sc-images-item-box">
                <div class="sc-images-item__img">
                  <img :src="nft.items[nft.currentItemIdx].img" alt="img">
                </div>
                <div class="sc-images-item-content">
                  <div class="sc-images-item-controls">
                    <div
                        class="control-arrow control-arrow_left sc-images-item-controls__arrow"
                        :class="{disabled: nft.currentItemIdx === 0}"
                        @click="prevImage(nft)"
                    />
                    <div class="sc-images-item-controls__name">
                      {{ isMobile ? 'Base type' : nft.platformName }}
                    </div>
                    <div
                        class="control-arrow control-arrow_right sc-images-item-controls__arrow"
                        :class="{disabled: nft.currentItemIdx >= nft.items.length - 1}"
                        @click="nextImage(nft)"
                    />
                  </div>
                  <div class="sc-images-item-info">
                    <div class="sc-images-item-info__rarity">{{ nft.items[nft.currentItemIdx].rarity }}</div>
                    <div class="sc-images-item-info__percent">{{ nft.items[nft.currentItemIdx].traitText }}</div>
                  </div>
                  <img :src="nft.graphImg" alt="graph" class="sc-images-item__graph"/>
                </div>
              </div>
            </div>
          </div>
          <img src="@/assets/img/ShowCase/bgStar.png" alt="" class="sc-images__bg-star-img desktop-only">
        </div>
      </div>
      <div class="sc-cloth-preview">
        <p class="sc-cloth-preview__text">
          With over 650 hours of work going into perfecting the CryptoDynasty avatars, you'll be able to appreciate even
          the smallest of details and textures.
        </p>
        <img src="@/assets/img/ShowCase/previewImg.png" alt="preview img" class="sc-cloth-preview__img"/>
      </div>
      <div class="sc-slider">
        <div class="sc-slider-left">
          <p class="sc-slider-left__text">Samples of accessory attributes </p>
          <div class="sc-slider-left-controls">
            <div ref="prevBtn" class="control-arrow control-arrow_left sc-slider-left-controls__arrow"/>
            <div ref="nextBtn" class="control-arrow control-arrow_right sc-slider-left-controls__arrow"/>
          </div>
        </div>
        <div class="sc-slider-swiper">
          <div class="swiper" ref="swiper">
            <div class="swiper-wrapper">
              <div class="swiper-slide" v-for="(slide, index) in slides" :key="index">
                <img :src="slide.img" :alt="slide.name" class="swiper-slide__img">
                <div class="swiper-slide-info">
                  <div class="swiper-slide-info__name">{{ slide.name }}</div>
                  <div class="swiper-slide-info__rarity">{{ slide.rarity }}</div>
                </div>
              </div>
            </div>
          </div>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
import Swiper from 'swiper';
import Bowser from 'bowser';

export default {
  name: "ShowCase",
  data() {
    const preloadImagesSources = [
      require('@/assets/img/ShowCase/nft/BNB Rare.png'),
      require('@/assets/img/ShowCase/nft/BNB Super Rare.png'),
      require('@/assets/img/ShowCase/nft/BNB Epic.png'),
      require('@/assets/img/ShowCase/nft/BNB Legendary.png'),
      require('@/assets/img/ShowCase/nft/BNB Mythic.png'),
      require('@/assets/img/ShowCase/nft/BTC Rare.png'),
      require('@/assets/img/ShowCase/nft/BTC Super Rare.png'),
      require('@/assets/img/ShowCase/nft/BTC Epic.png'),
      require('@/assets/img/ShowCase/nft/BTC Legendary.png'),
      require('@/assets/img/ShowCase/nft/BTC Mythic.png'),
      require('@/assets/img/ShowCase/nft/DOGE Rare.png'),
      require('@/assets/img/ShowCase/nft/DOGE Super Rare.png'),
      require('@/assets/img/ShowCase/nft/DOGE Epic.png'),
      require('@/assets/img/ShowCase/nft/DOGE Legendary.png'),
      require('@/assets/img/ShowCase/nft/DOGE Mythic.png'),
      require('@/assets/img/ShowCase/nft/ADA Rare.png'),
      require('@/assets/img/ShowCase/nft/ADA Super Rare.png'),
      require('@/assets/img/ShowCase/nft/ADA Epic.png'),
      require('@/assets/img/ShowCase/nft/ADA Legendary.png'),
      require('@/assets/img/ShowCase/nft/ADA Mythic.png'),
      require('@/assets/img/ShowCase/nft/ETH Rare.png'),
      require('@/assets/img/ShowCase/nft/ETH Super Rare.png'),
      require('@/assets/img/ShowCase/nft/ETH Epic.png'),
      require('@/assets/img/ShowCase/nft/ETH Legendary.png'),
      require('@/assets/img/ShowCase/nft/ETH Mythic.png')
    ]
  
    preloadImagesSources.forEach(imgSrc => {
      (new Image()).src = imgSrc;
    })
    
    return {
      currentBaseSlideIdx: 0,
      browser: Bowser.getParser(window.navigator.userAgent),
      slider: null,
      nfts: [
        {
          platformName: 'Binance',
          currentItemIdx: 0,
          graphImg: require('@/assets/img/ShowCase/nft/graphBinance.png'),
          items: [
            {
              rarity: 'Rare',
              img: require('@/assets/img/ShowCase/nft/BNB Rare.png'),
              traitText: '10.00% have this trait'
            },
            {
              rarity: 'Super Rare',
              img: require('@/assets/img/ShowCase/nft/BNB Super Rare.png'),
              traitText: '5.50% have this trait'
            },
            {
              rarity: 'Epic',
              img: require('@/assets/img/ShowCase/nft/BNB Epic.png'),
              traitText: '3.33% have this trait'
            },
            {
              rarity: 'Legendary',
              img: require('@/assets/img/ShowCase/nft/BNB Legendary.png'),
              traitText: '1.11% have this trait'
            },
            {
              rarity: 'Mythic',
              img: require('@/assets/img/ShowCase/nft/BNB Mythic.png'),
              traitText: '0.06% have this trait'
            }
          ]
        },
        {
          platformName: 'Bitcoin',
          currentItemIdx: 0,
          graphImg: require('@/assets/img/ShowCase/nft/btcGraph.png'),
          items: [
            {
              rarity: 'Rare',
              img: require('@/assets/img/ShowCase/nft/BTC Rare.png'),
              traitText: '10.00% have this trait'
            },
            {
              rarity: 'Super Rare',
              img: require('@/assets/img/ShowCase/nft/BTC Super Rare.png'),
              traitText: '5.50% have this trait'
            },
            {
              rarity: 'Epic',
              img: require('@/assets/img/ShowCase/nft/BTC Epic.png'),
              traitText: '3.33% have this trait'
            },
            {
              rarity: 'Legendary',
              img: require('@/assets/img/ShowCase/nft/BTC Legendary.png'),
              traitText: '1.11% have this trait'
            },
            {
              rarity: 'Mythic',
              img: require('@/assets/img/ShowCase/nft/BTC Mythic.png'),
              traitText: '0.06% have this trait'
            }
          ]
        },
        {
          platformName: 'Dogecoin',
          currentItemIdx: 0,
          graphImg: require('@/assets/img/ShowCase/nft/dogeGraph.png'),
          items: [
            {
              rarity: 'Rare',
              img: require('@/assets/img/ShowCase/nft/DOGE Rare.png'),
              traitText: '10.00% have this trait'
            },
            {
              rarity: 'Super Rare',
              img: require('@/assets/img/ShowCase/nft/DOGE Super Rare.png'),
              traitText: '5.50% have this trait'
            },
            {
              rarity: 'Epic',
              img: require('@/assets/img/ShowCase/nft/DOGE Epic.png'),
              traitText: '3.33% have this trait'
            },
            {
              rarity: 'Legendary',
              img: require('@/assets/img/ShowCase/nft/DOGE Legendary.png'),
              traitText: '1.11% have this trait'
            },
            {
              rarity: 'Mythic',
              img: require('@/assets/img/ShowCase/nft/DOGE Mythic.png'),
              traitText: '0.06% have this trait'
            }
          ]
        },
        {
          platformName: 'Cardano',
          currentItemIdx: 0,
          graphImg: require('@/assets/img/ShowCase/nft/adaGraph.png'),
          items: [
            {
              rarity: 'Rare',
              img: require('@/assets/img/ShowCase/nft/ADA Rare.png'),
              traitText: '10.00% have this trait'
            },
            {
              rarity: 'Super Rare',
              img: require('@/assets/img/ShowCase/nft/ADA Super Rare.png'),
              traitText: '5.50% have this trait'
            },
            {
              rarity: 'Epic',
              img: require('@/assets/img/ShowCase/nft/ADA Epic.png'),
              traitText: '3.33% have this trait'
            },
            {
              rarity: 'Legendary',
              img: require('@/assets/img/ShowCase/nft/ADA Legendary.png'),
              traitText: '1.11% have this trait'
            },
            {
              rarity: 'Mythic',
              img: require('@/assets/img/ShowCase/nft/ADA Mythic.png'),
              traitText: '0.06% have this trait'
            }
          ]
        },
        {
          platformName: 'Ethereum',
          currentItemIdx: 0,
          graphImg: require('@/assets/img/ShowCase/nft/ethGraph.png'),
          items: [
            {
              rarity: 'Rare',
              img: require('@/assets/img/ShowCase/nft/ETH Rare.png'),
              traitText: '10.00% have this trait'
            },
            {
              rarity: 'Super Rare',
              img: require('@/assets/img/ShowCase/nft/ETH Super Rare.png'),
              traitText: '5.50% have this trait'
            },
            {
              rarity: 'Epic',
              img: require('@/assets/img/ShowCase/nft/ETH Epic.png'),
              traitText: '3.33% have this trait'
            },
            {
              rarity: 'Legendary',
              img: require('@/assets/img/ShowCase/nft/ETH Legendary.png'),
              traitText: '1.11% have this trait'
            },
            {
              rarity: 'Mythic',
              img: require('@/assets/img/ShowCase/nft/ETH Mythic.png'),
              traitText: '0.06% have this trait'
            }
          ]
        },
      ],
      slides: [
        {
          img: require('@/assets/img/ShowCase/slider/Bomber Jacket College.png'),
          name: 'Bomber Jacket College',
          rarity: 'Rarity 6.0%',
        },
        {
          img: require('@/assets/img/ShowCase/slider/Bucket Hat.png'),
          name: 'Bucket Hat',
          rarity: 'Rarity 7.5%',
        },
        {
          img: require('@/assets/img/ShowCase/slider/Crown.png'),
          name: 'Crown',
          rarity: 'Rarity 3.0%',
        },
        {
          img: require('@/assets/img/ShowCase/slider/Futuristic Glasses.png'),
          name: 'Futuristic Glasses',
          rarity: 'Rarity 2.5%',
        },
        {
          img: require('@/assets/img/ShowCase/slider/Headphones.png'),
          name: 'Headphones',
          rarity: 'Rarity 3.5%',
        },
        {
          img: require('@/assets/img/ShowCase/slider/Leather Jacket.png'),
          name: 'Leather Jacket',
          rarity: 'Rarity 4.0%',
        },
        {
          img: require('@/assets/img/ShowCase/slider/Racer Helmet.png'),
          name: 'Racer Helmet',
          rarity: 'Rarity 6.0%',
        },
        {
          img: require('@/assets/img/ShowCase/slider/Shark Chain.png'),
          name: 'Shark Chain',
          rarity: 'Rarity 6.0%',
        },
        {
          img: require('@/assets/img/ShowCase/slider/Vest.png'),
          name: 'Vest',
          rarity: 'Rarity 2.5%',
        },
        {
          img: require('@/assets/img/ShowCase/slider/VR Glasses.png'),
          name: 'VR Glasses',
          rarity: 'Rarity 3.0%',
        },
      ],
      baseTypeSlider: null,
    }
  },
  mounted() {
    console.log('123')
    this.slider = new Swiper(this.$refs.swiper, {
      spaceBetween: 36,
      slidesPerView: 'auto',
      centeredSlides: false,
      loop: true,
      breakpoints: {
        1024: {
          slidesPerView: 2,
        }
      }
    })

    this.$refs.nextBtn.addEventListener('click', () => this.handleNextSlide(this.slider))
    this.$refs.prevBtn.addEventListener('click', () => this.handlePrevSlide(this.slider))
  
    if (this.isMobile) {
      this.baseTypeSlider = new Swiper(this.$refs.imagesSwiper, {
        slidesPerView: 1,
        spaceBetween: 48,
        centeredSlides: true,
        breakpoints: {
          720: {
            slidesPerView: 2,
          },
          1100: {
            slidesPerView: 3,
          },
        }
      })

      this.baseTypeSlider.on('activeIndexChange', (swiper) => {
        this.currentBaseSlideIdx = swiper.activeIndex
      })

      this.$refs.nextBaseBtn.addEventListener('click', () => this.handleNextSlide(this.baseTypeSlider))
      this.$refs.prevBaseBtn.addEventListener('click', () => this.handlePrevSlide(this.baseTypeSlider))
  
    }
  },
  methods: {
    handleNextSlide(slider) {
      slider.slideNext()
    },
    handlePrevSlide(slider) {
      slider.slidePrev()
    },
    prevImage(nft) {
      if (nft.currentItemIdx === 0) {
        return
      }

      nft.currentItemIdx--;
    },
    nextImage(nft) {
      if (nft.currentItemIdx >= nft.items.length - 1) {
        return
      }

      nft.currentItemIdx++;
    },
  },
  computed: {
    isMobile() {
      return this.browser.getPlatform()?.type === 'mobile'
    },
    currentBaseSlidePlatform() {
      return this.nfts[this.currentBaseSlideIdx]?.platformName ?? '...'
    },
    allowSlides() {
      return {
        prev: this.currentBaseSlideIdx > 0,
        next: this.currentBaseSlideIdx < this.nfts.length - 1,
      }
    }
  },
  beforeDestroy() {
    this.$refs.nextBtn.removeEventListener('click', this.handleNextSlide)
    this.$refs.prevBtn.removeEventListener('click', this.handlePrevSlide)
  }
}
</script>

<style scoped lang="scss">
@import "~@/assets/scss/components/ShowCase.scss";
</style>