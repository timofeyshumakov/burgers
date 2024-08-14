<script>
import List from './List.vue';
import Img from './Img.vue';
import Button from './Button.vue';
const sectionName = "header";
export default {
  components: { List, Img, Button },
  data() {
    return {
      isMobile: window.innerWidth < 767,
      isMenuOpen: false,
      sectionName,
      litem: [
        {txt: "Почему у нас", link: "#"},
        {txt: "Меню бургеров", link: "#"},
        {txt: "Оформление заказа", link: "#"},
      ],
    }
  },
  mounted() {
    window.addEventListener('resize', this.handleResize);
  },
  methods: {
    
    handleResize() {
      this.isMobile = window.innerWidth < 767;
      if (this.isMobile) {
        this.isMenuOpen = false;
      }else{
        this.isMenuOpen = true;
      }
    },
    toggleMenu() {
      if (this.isMenuOpen) {
        this.isMenuOpen = false;
      }else{
        this.isMenuOpen = true;
      }
    },
  },
};
</script>

<template>
  <header class="header">
    <div class="header__container container" ref="headerContainer" id="headerContainer">
      <a class="header__logo logo" href="#" id="header__logo">
        <Img class="header__logo" src="logo.svg" alt="some photo"/>
      </a>
      <div v-if="isMobile" class="burger-menu" :class="{ 'burger-active' : isMenuOpen }" @click="toggleMenu">
          <span class="burger-line" v-for="i in 3"></span>
      </div>
      <nav class="header__menu header-menu menu-burger-content" :class="{ 'burger-active' : isMenuOpen }" id="menu-burger-content">
        <List sectionName="header-menu" :litem/>
      </nav>
      <Button buttonClassName="header__button button" txt="$"/>
    </div>
  </header>
</template>

<style scoped lang="sass">
@import "../vars.sass"

.header
  padding: 2.3rem 0

.container
  flex-direction: row
  gap: min(7vw, 2rem)



</style>