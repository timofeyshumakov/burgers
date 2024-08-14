<script>
import Img from './Img.vue';
import Button from './Button.vue';
const sectionName = "header";
export default {
  components: { Img, Button },
}
</script>
<template>
    <section class="main__order order section-bg">
        <div class="order__container container">
            <h2 class="order__title title">оформление заказа</h2>
            <div class="order__body">
                <Img class="order__img" src="order_image.png"/>
                <form class="order__form" action="/search" method="get">
                    <h4 class="order__form-title">Заполните все данные и наш менеджер свяжется с вами для подтверждения заказа</h4>
                    <div class="order__input-wrapper">
                        <input class="order__input" type="text" name="order" placeholder="Ваш заказ">
                    </div>
                    <div class="order__input-wrapper">
                        <input class="order__input" type="text" name="name" placeholder="Ваше имя">
                    </div>
                    <div class="order__input-wrapper">
                        <input class="order__input" type="tel" name="phone" placeholder="Ваш телефон">
                    </div>
                    <Button buttonClassName="order__button button primary-button" txt="Оформить заказ"/>
                </form>
            </div>
        </div>
    </section>
</template>

<style scoped lang="sass">
@import "../vars.sass"

.order
    background-image: url(../assets/img/order_bg.png)
    background-position-x: right

.order__

    &body
        display: flex
        align-items: center
        position: relative
        left: -15rem
        top: -9.5rem

    &img
        position: relative
        right: -5.5rem

    &form
        display: flex
        flex-direction: column
        width: 26.5rem
        padding: 3.7rem 2.5rem
        gap: 1.25rem
        border: 1px solid $dark-grey
        border-radius: 1rem
        background: $cards
        height: fit-content

    &form-title
        font-size: 1.45rem
        text-align: center
        font-weight: 600
        margin-bottom: 1.25rem

    &input-wrapper
        padding: 2px
        border-radius: 0.5rem
        background: linear-gradient(to right, #DA8023, #E2B438)

    &input
        height: 4rem
        background: $cards
        width: 100%
        border-radius: 0.5rem
        padding: 1rem 0.6rem
        font-weight: 600
        font-size: 16px
        line-height: 140%
        color: $white

    &input::placeholder
        color: $grey

    &button
        width: 100%

</style>