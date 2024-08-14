<script>
const sectionName = "footer";
import Img from './Img.vue'
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
  components: { Img }
};
</script>

<template>
    <footer class="footer" ref="sectionRef">
        <div class="footer__container container">
          <Img src="logo.svg"/>
          <div class="copyright">Все права защищены</div>
        </div>
    </footer>
</template>



<style scoped lang="sass">
@import "../vars.sass"

.footer
  margin-top: -12rem
  padding: 3.15rem 0

.container
  flex-direction: row

</style>