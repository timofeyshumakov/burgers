<script>
import Img from './Img.vue';
  export default {
    components: { Img },
    props: {
        card: Object
    }
  }
</script>
<template>
    <div class="card">
        <Img class="card__img" :src="card.img.src"/>
        <div class="card__title">{{ card.title }}</div>
        <div class="card__txt txt">{{ card.txt }}</div>
    </div>
</template>
<style scoped lang="sass">
@import "../vars.sass"

.card
  display: flex
  flex-direction: column
  gap: 1.5rem
  text-align: center
  align-items: center
  max-width: 23.5rem

.card__

  &img
    width: 6.5rem
    height: 6.5rem

  &title
    font-size: 1.5rem

  &txt
    text-align: center

</style>