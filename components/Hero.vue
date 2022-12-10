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
  </div>
</template>

<style scoped lang="scss">
.hero {
  height: 80vh;
  width: 100vw;
  display: flex;
  flex-direction: column;
  align-items: center;
  justify-content: center;
  gap: 2rem;
  font-size: 1.5rem;
  line-height: 1.2;
  &__name {
    font-weight: 600;
    font-size: 2em;
  }
  &__text {
    display: block;
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
}
</style>