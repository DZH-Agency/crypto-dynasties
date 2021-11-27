<template>
  <div class="sc-wrapper">
    <div class="container">
      <div class="sc">
        <h3 class="sc__title">Inside The DNA Of CryptoDynasties</h3>
        <p class="sc__text">
          CryptoDynasties is a 3D art collection where every attribute was curated and designed with an exceptional
          attention to detail to produce the most unique NFT avatars on the market today. The end result took over two
          months of brainstorming sessions and careful craftsmanship to give form to some of the biggest CryptoDynasties
          leading the revolution today: Bitcoin, Ethereum, Binance Coin, Cardano and Dogecoin.
        </p>
        <div class="sc-images">
          <div class="sc-images-item" v-for="nft in nfts" :key="nft.platformName">
            <div class="sc-images-item__img">
              <img :src="nft.items[nft.currentItemIdx].img" alt="img">
            </div>
            <div class="sc-images-item-content">
              <div class="sc-images-item-controls">
                <div
                    class="sc-images-item-controls__arrow sc-images-item-controls__arrow_left"
                    :class="{disabled: nft.currentItemIdx === 0}"
                    @click="prevImage(nft)"
                />
                <div class="sc-images-item-controls__name">{{ nft.platformName }}</div>
                <div
                    class="sc-images-item-controls__arrow sc-images-item-controls__arrow_right"
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
    </div>
  </div>
</template>

<script>
export default {
  name: "ShowCase",
  data() {
    return {
      nfts: [
        {
          platformName: 'Binance',
          currentItemIdx: 0,
          graphImg: require('@/assets/img/ShowCase/nft/graphBinance.png'),
          items: [
            {
              rarity: 'Legendary',
              img: require('@/assets/img/ShowCase/nft/BitcoinLegendary.png'),
              traitText: '0.05% have this trait'
            },
            {
              rarity: 'Super Rare',
              img: require('@/assets/img/ShowCase/nft/BinanceSuperRare.png'),
              traitText: '7.50% have this trait'
            },
            {
              rarity: 'Epic',
              img: require('@/assets/img/ShowCase/nft/DogecoinEpic.png'),
              traitText: '2.45% have this trait'
            },
            {
              rarity: 'Rare',
              img: require('@/assets/img/ShowCase/nft/CardanoRare.png'),
              traitText: '10.00% have this trait'
            },
            {
              rarity: 'Rare',
              img: require('@/assets/img/ShowCase/nft/EthereumRare.png'),
              traitText: '10.00% have this trait'
            },
          ]
        },
        {
          platformName: 'Binance',
          currentItemIdx: 0,
          graphImg: require('@/assets/img/ShowCase/nft/graphBinance.png'),
          items: [
            {
              rarity: 'Legendary',
              img: require('@/assets/img/ShowCase/nft/BitcoinLegendary.png'),
              traitText: '0.05% have this trait'
            },
            {
              rarity: 'Super Rare',
              img: require('@/assets/img/ShowCase/nft/BinanceSuperRare.png'),
              traitText: '7.50% have this trait'
            },
            {
              rarity: 'Epic',
              img: require('@/assets/img/ShowCase/nft/DogecoinEpic.png'),
              traitText: '2.45% have this trait'
            },
            {
              rarity: 'Rare',
              img: require('@/assets/img/ShowCase/nft/CardanoRare.png'),
              traitText: '10.00% have this trait'
            },
            {
              rarity: 'Rare',
              img: require('@/assets/img/ShowCase/nft/EthereumRare.png'),
              traitText: '10.00% have this trait'
            },
          ]
        },
        {
          platformName: 'Binance',
          currentItemIdx: 0,
          graphImg: require('@/assets/img/ShowCase/nft/graphBinance.png'),
          items: [
            {
              rarity: 'Legendary',
              img: require('@/assets/img/ShowCase/nft/BitcoinLegendary.png'),
              traitText: '0.05% have this trait'
            },
            {
              rarity: 'Super Rare',
              img: require('@/assets/img/ShowCase/nft/BinanceSuperRare.png'),
              traitText: '7.50% have this trait'
            },
            {
              rarity: 'Epic',
              img: require('@/assets/img/ShowCase/nft/DogecoinEpic.png'),
              traitText: '2.45% have this trait'
            },
            {
              rarity: 'Rare',
              img: require('@/assets/img/ShowCase/nft/CardanoRare.png'),
              traitText: '10.00% have this trait'
            },
            {
              rarity: 'Rare',
              img: require('@/assets/img/ShowCase/nft/EthereumRare.png'),
              traitText: '10.00% have this trait'
            },
          ]
        },
        {
          platformName: 'Binance',
          currentItemIdx: 0,
          graphImg: require('@/assets/img/ShowCase/nft/graphBinance.png'),
          items: [
            {
              rarity: 'Legendary',
              img: require('@/assets/img/ShowCase/nft/BitcoinLegendary.png'),
              traitText: '0.05% have this trait'
            },
            {
              rarity: 'Super Rare',
              img: require('@/assets/img/ShowCase/nft/BinanceSuperRare.png'),
              traitText: '7.50% have this trait'
            },
            {
              rarity: 'Epic',
              img: require('@/assets/img/ShowCase/nft/DogecoinEpic.png'),
              traitText: '2.45% have this trait'
            },
            {
              rarity: 'Rare',
              img: require('@/assets/img/ShowCase/nft/CardanoRare.png'),
              traitText: '10.00% have this trait'
            },
            {
              rarity: 'Rare',
              img: require('@/assets/img/ShowCase/nft/EthereumRare.png'),
              traitText: '10.00% have this trait'
            },
          ]
        },
        {
          platformName: 'Binance',
          currentItemIdx: 0,
          graphImg: require('@/assets/img/ShowCase/nft/graphBinance.png'),
          items: [
            {
              rarity: 'Legendary',
              img: require('@/assets/img/ShowCase/nft/BitcoinLegendary.png'),
              traitText: '0.05% have this trait'
            },
            {
              rarity: 'Super Rare',
              img: require('@/assets/img/ShowCase/nft/BinanceSuperRare.png'),
              traitText: '7.50% have this trait'
            },
            {
              rarity: 'Epic',
              img: require('@/assets/img/ShowCase/nft/DogecoinEpic.png'),
              traitText: '2.45% have this trait'
            },
            {
              rarity: 'Rare',
              img: require('@/assets/img/ShowCase/nft/CardanoRare.png'),
              traitText: '10.00% have this trait'
            },
            {
              rarity: 'Rare',
              img: require('@/assets/img/ShowCase/nft/EthereumRare.png'),
              traitText: '10.00% have this trait'
            },
          ]
        },
      ]
    }
  },
  methods: {
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
  }
}
</script>

<style scoped lang="scss">
@import "~@/assets/scss/components/ShowCase.scss";
</style>