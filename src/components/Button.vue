<script>
export default {
  props: ['link', 'txt', 'buttonClassName', 'formClassName']
}
</script>

<template>
    <form v-if="formClassName !== undefined" :class="formClassName" :action="link">
        <button :class="buttonClassName">{{ txt }}</button>
    </form>
    <button v-else :class="buttonClassName">{{ txt }}</button>
</template>

<style scoped lang="sass">

@import "../vars.sass"

.primary-button
  background: linear-gradient(135deg, #da8023 0%, #e2b438 100%)
  border-radius: 0.5rem
  padding: 1.25rem 4rem
  width: fit-content
  font-size: 1.15rem
  text-align: center

.header__button
  width: 3rem
  height: 3rem
  border: 1px solid $white
  border-radius: 0.3rem
  background: transparent
  color: $white

</style>