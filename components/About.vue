<template>
  <section class="about">
    <h2 class="about__title">
      About me.
    </h2>
    <div class="about__content">
      <p class="about__paragraph">
        I'm a frontend developer who builds web applications with Vue. I enjoy turning
        designs into fast, accessible interfaces that feel good to use, from the first
        click to the last detail.
      </p>
      <p class="about__paragraph">
        Most of my day-to-day work happens in the Vue ecosystem: Nuxt, TypeScript,
        Sass and a healthy amount of animation. This page itself is built with Nuxt 3,
        and the waves above are drawn with GSAP.
      </p>
      <p class="about__paragraph">
        I care about clean, readable code and good collaboration with designers and
        backend developers. I like small, well-tested components and interfaces that
        stay simple as the product grows.
      </p>
      <p class="about__paragraph">
        If you have a project in mind or just want to talk about frontend, feel free to
        reach out by email.
      </p>
    </div>
  </section>
</template>

<script lang="ts">
export default defineComponent({
  name: "About",
})
</script>

<style scoped lang="scss">
.about {
  display: flex;
  flex-direction: column;
  align-items: center;
  padding: 4rem 1rem 6rem;
  line-height: 1.6;
  &__title {
    font-weight: 600;
    font-size: 2rem;
    margin-bottom: 2rem;
  }
  &__content {
    display: flex;
    flex-direction: column;
    gap: 1.5rem;
    max-width: 50rem;
  }
  &__paragraph {
    font-size: 1rem;
    letter-spacing: 1px;
  }
  @media(max-width: 1000px) {
    align-items: flex-start;
    padding: 2rem 1rem 4rem;
    &__title {
      font-size: 1.5rem;
    }
  }
}
</style>
