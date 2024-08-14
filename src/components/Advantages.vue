<script>
import Img from './Img.vue';
import Button from './Button.vue';
import AdvantagesCard from './AdvantagesCard.vue';
const sectionName = "advantages";
const format = "png";
import { ref, onMounted } from 'vue'
export default {
  setup() {
    const sectionRef = ref(null)

    onMounted(() => {
      const observer = new IntersectionObserver((entries) => {
        entries.forEach((entry) => {
          if (entry.isIntersecting) {
            setTimeout(() => {
              sectionRef.value.classList.add('fade-in')
            }, 100)
            observer.unobserve(entry.target)
          }
        })
      })
      observer.observe(sectionRef.value)
    })

    return {
      sectionRef,
    }
  },
  components: { Img, Button, AdvantagesCard},
  data() {
    return {
        sectionName: "advantages",
        cards: [
            {txt: "Наши бургеры обладают уникальным сочетанием вкусов и не похожи ни на какие другие. Мы тщательно отбираем лучшие ингредиенты и сочетания вкусов для нашего меню.", title: "Авторские рецепты" ,img:{src: `${sectionName}/burger.${format}`}},
            {txt: "Для наших бургеров мы используем отборную 100% мраморную говядину, которую закупаем исключительно у фермеров. Мы уверены в качестве нашего мяса.", title: "Мраморная говядина" , img:{src: `${sectionName}/meat.${format}`}},
            {txt: "Мы доставляем в пределах МКАД за 30 минут, а если не успеем — доставка бесплатно. Мы тщательно упаковываем наши бургеры, чтобы по дороге они не остыли.", title: "Быстрая доставка" , img:{src: `${sectionName}/food_truck.${format}`}}
        ],
    }
    },
}
</script>
<template>
    <section class="advantages section-bg" :id="sectionName" ref="sectionRef">
      <div class="container">
        <h2 class="advantages__title title">почему нас выбирают?</h2>
        <div class="cards">
            <AdvantagesCard v-for="card in cards" :card="card" />
        </div>
      </div>
    </section>
</template>
<style scoped lang="sass">
@import "../vars.sass"

.advantages
  background-image: url(../assets/img/whybg.png)


.container
  flex-direction: column

.cards
    display: grid
    grid-template-columns: repeat(3, 1fr)
    gap: 8.5%

</style>