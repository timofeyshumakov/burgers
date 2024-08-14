<script>
import Img from './Img.vue';

  export default {
    components: { Img },
    props: {
      litem: Object,
      markSheme: String,
      tariffsIndex: Number,
      sectionName: String
    },
  }
</script>
<template>
    <ul :class = "`${sectionName}__list list`">
        <li v-if="sectionName !== 'faq'" :class = "`${sectionName}__item item`" v-for="(item, index) in litem">
          <a v-if="item.link !== '' && item.link !== undefined"  :href="`${item.link}`" :class = "`${sectionName}__link link`">{{ item.txt }}</a>
          <span v-if="sectionName === 'header-menu'" class="link-decor"></span>
        </li>
    </ul>
</template>

<style lang="sass">

@import "../vars.sass"

.header-menu
  display: flex
  flex-direction: row
  gap: min(7vw, 9rem)

.header-menu__
  
  &list
    display: flex
    flex-direction: row
    align-items: center
    gap: min(5vw, 5.5rem)

  &item
    position: relative

  &link
    font-weight: 500
    font-size: 1.15rem
    color: $white
    font-family: $ff1
    
  &link:hover
    color: $red
    transition: $transition

  &link:hover ~ .link-decor
    transition: $transition
    width: 100%
    display: inline-block
    background: $red
    height: 2px

.link-decor
  width: 0
  position: absolute
  bottom: -0.5rem
  left: 0

</style>