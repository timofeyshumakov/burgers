<script setup lang="ts">
import './reset.css'
import TheHeader from './components/TheHeader.vue'
import TheFooter from './components/TheFooter.vue'
import Promo from './components/Promo.vue'
import Advantages from './components/Advantages.vue'
import Catalog from './components/Catalog.vue'
import Order from './components/Order.vue'
</script>

<template>
  <div class="wrapper section-bg">
    <TheHeader/>
    <main class="main">
      <Promo/>
      <Advantages/>
      <Catalog/>
      <Order/>
    </main>
    <TheFooter/>
  </div>
</template>

<style lang="sass">
@import "vars.sass"

@font-face
  font-style: regular
  font-weight: 400
  font-display: swap
  font-family: "Gilroy"
  src: local("Gilroy-Regular")
  src: url("assets/fonts/Gilroy-Regular.woff2") format("woff2")
  src: url("assets/fonts/Gilroy-Regular.woff") format("woff")
  src: url("assets/fonts/Gilroy-Regular.ttf") format("ttf")

  font-style: regular
  font-weight: 400
  font-display: swap
  font-family: "Merriweather"
  src: local("Merriweather-Regular")
  src: url("assets/fonts/Merriweather-Regular.woff2") format("woff2")
  src: url("assets/fonts/Merriweather-Regular.woff") format("woff")
  src: url("assets/fonts/Merriweather-Regular.ttf") format("ttf")

/*#scrollbar*/
::-webkit-scrollbar-track
  background-color: $white

::-webkit-scrollbar-thumb
  background-color: $red
  border-radius: 0.5rem

::-webkit-scrollbar-thumb:active
  background-color: $red

::-webkit-scrollbar
  width: 0.6rem

/*#common*/
html
  font: 600 16px /1.2 $ff1

body
  scroll-behavior: smooth
  background: $bg
  color: $white

#app
  overflow-x: hidden

.section-bg
  background-repeat: no-repeat
  background-position-x: center
  background-size: cover
  width: 100%
  
.wrapper
  background-image: url(../assets/img/main_bg.png)
  margin: 0 auto
  background-size: contain
  width: 100vw



.main
  position: relative
  top: -4rem

.container
  display: flex
  padding: 0 2rem
  margin: 0 auto
  box-sizing: content-box
  max-width: 75rem
  justify-content: space-between
  align-items: center
  flex-direction: column
  gap: 3.75rem

.txt
  line-height: 140%
  text-align: center
  text-align: start

.title
  font: 900 4rem /1 $ff2
  letter-spacing: 0.03em
  text-transform: uppercase
  text-align: center

/*#modifficators*/

/*media*/
@media screen and (min-width: 135rem)

  .wrapper
    max-width: 120rem
  
</style>
