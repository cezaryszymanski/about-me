<template>
  <div class="hero">
    <h1 class="hero__name">
      Cezary Szymański.
    </h1>
    <span class="hero__text">
      Frontend Developer (Vue).
    </span>
    <span class="hero__text">
      Contact me: <a href="mailto:cezszym@protonmail.com">cezszym@protonmail.com</a>
    </span>
    <div class="hero__dots">
      <div v-for="dot in dots" :key="dot" class="hero__dot" :class="`hero__dot--${dot}`" />
    
    </div>
  </div>
</template>

<script lang="ts">
import { gsap } from "gsap";
import { useWindowSize } from '@vueuse/core'

export default defineComponent({

  name: "Hero",

  setup() {

    const { width: screenWidth, height: screenHeight } = useWindowSize()

    const dots = Array.from({ length: 100}).map((el, index) => index)


    onMounted(() => {
      dots.forEach((dot) => {

        const sign = dot % 2 === 0 ? 1 : -1

        gsap.to(`.hero__dot--${dot}`, {y: sign * screenHeight.value / 4 , duration: 1, opacity: 0, repeat: -1, yoyo: true, delay: dot / 30  })
      })
    })

    return {
      screenWidth,
      dots
    }
  }
  
})

</script>

<style scoped lang="scss">
.hero {
  height: 80vh;
  width: 100vw;
  display: flex;
  flex-direction: column;
  align-items: center;
  justify-content: center;
  font-size: 1.5rem;
  line-height: 1.2;
  overflow-x: hidden;
  &__name {
    font-weight: 600;
    font-size: 2em;
  }
  &__text {
    display: block;
    margin: 1rem 0;
  }
  @media(max-width: 1000px) {
    align-items: flex-start;
    font-size: 1rem;
    padding: 1rem;
    a {
      margin-top: 1rem;
      padding: .5rem 1rem;
      display: block;
    }
  }
  &__dots {
    display: flex;
    margin-top: 0.2rem;
  }
  &__dot {
   height: 10px;
   width: 10px;
   background: var(--primary);
   margin-right: 2px;
   border-radius: 50%;
  }
}

</style>