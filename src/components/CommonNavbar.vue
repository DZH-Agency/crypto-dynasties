<template>
  <div>
    <div class="navbar-wrapper">
      <div class="container">
        <div class="navbar">
          <img src="@/assets/img/CommonNavbar/Logo.png" alt="logo" class="navbar__logo">
          <div class="navbar-menu desktop-only">
            <a
                class="navbar-menu__item"
                v-for="(item, index) in navbarItems"
                :key="index"
                :href="item.link"
            >
              {{ item.title }}
            </a>
          </div>
          <img @click="isOpened = !isOpened" src="@/assets/img/menuIcon.png" alt="open">
        </div>
      </div>
    </div>
    <div class="navbar-mobile-wrapper" :class="{opened: isOpened}">
        <div class="navbar-mobile">
          <div class="navbar-mobile-top">
            <img src="@/assets/img/CommonNavbar/Logo.png" alt="logo" class="navbar__logo">
            <img @click="isOpened = !isOpened" src="@/assets/img/menuClose.png" alt="open">
          </div>
          <div class="navbar-mobile-menu">
            <a
                class="navbar-mobile-menu__item"
                v-for="(item, index) in navbarItems"
                :key="index"
                :href="item.link"
                @click="isOpened = false"
            >
              {{ item.title }}
            </a>
          </div>
        </div>
    </div>
  </div>
</template>

<script>
export default {
  name: "CommonNavbar",
  watch: {
    // isOpened(newVal) {
    //   document.body.classList.toggle('scroll-lock')
    // }
  },
  data() {
    return {
      isOpened: true,
      navbarItems: [
        {
          title: 'Home',
          link: '#'
        },
        {
          title: 'Story',
          link: '#story'
        },
        {
          title: 'About',
          link: '#about'
        },
        {
          title: 'Artist',
          link: '#artist'
        },
        {
          title: 'FAQ',
          link: '#faq'
        },
      ]
    }
  }
}
</script>

<style scoped lang="scss">
@import "~@/assets/scss/components/CommonNavbar.scss";
</style>