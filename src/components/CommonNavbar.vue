<template>
  <div class="navbar-wrapper">
    <div class="container">
      <div class="navbar">
        <img src="@/assets/img/CommonNavbar/Logo.png" alt="">
        <div class="navbar-menu">
          <a
              class="navbar-menu__item"
              v-for="(item, index) in navbarItems"
              :key="index"
              :href="item.link"
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
  data() {
    return {
      navbarItems: [
        {
          title: 'Home',
          link: '#'
        },
        {
          title: 'Story',
          link: '#'
        },
        {
          title: 'About',
          link: '#'
        },
        {
          title: 'Artist',
          link: 'FAQ'
        },
        {
          title: '',
          link: ''
        },
      ]
    }
  }
}
</script>

<style scoped lang="scss">
@import "~@/assets/scss/components/CommonNavbar.scss";
</style>