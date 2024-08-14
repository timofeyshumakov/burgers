<script>
import Img from './Img.vue';
import Button from './Button.vue';
const sectionName = "header";
export default {
  components: { Img, Button },
}
</script>
<template>
    <div class="promo__container container">
        <div class="promo__info">
            <div class="promo__header">
                <span class="promo__decor">Новое меню</span>
                <h1 class="promo__title title">бургер чеддер</h1>
            </div>
            <div class="promo__txt txt">Мы обновили наше меню, спешите попробовать сезонные новинки и насладиться отличным вкусом наших бургеров. Готовим для вас лучшие бургеры в городе из отборной мраморной говядины.</div>
            <Button buttonClassName="promo__button button primary-button" txt="Смотреть меню"/>
        </div>
        <Img class="promo__img" src="main_burger.png"/>
    </div>
</template>

<style scoped lang="sass">
@import "../vars.sass"

.promo__

    &container
        flex-direction: row

    &info
        max-width: 38rem
        display: flex
        flex-direction: column
        gap: 3.5rem

    &img
        position: relative
        left: -20rem
        top: 2rem

    &decor
        font-size: 1.15rem
        border-radius: 6.5rem
        padding: 0.75rem 1rem
        background: $red
        line-height: 1.3
        width: fit-content
        display: inline-block

    &title
        text-align: start
        font-size: 7.5rem
        line-height: 1.3

    &txt
        font-size: 1.28rem

</style>