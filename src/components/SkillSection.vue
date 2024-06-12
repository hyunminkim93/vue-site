<script setup>
import { skillText } from '@/constants'
</script>

<template>
  <section id="skill">
    <div class="skill__inner">
      <div class="skill__title">
        <h2>Challenge <em>나의 도전</em></h2>
      </div>
      <div class="skill__desc">
        <div v-for="(text, key) in skillText" :key="key">
          <span>{{ key + 1 }}.</span>
          <h3>{{ text.title }}</h3>
          <p>{{ text.description }}</p>
        </div>
      </div>
    </div>
  </section>
</template>

<style lang="scss" scoped>
#skill {
  min-height: 100vh;
}
.skill__inner {
  padding: 16px;
  display: flex;
  justify-content: space-between;

  @media (max-width: 800px) {
    flex-direction: column;
  }

  .skill__title {
    position: sticky;
    top: 100px;
    left: 0;
    width: 48%;
    height: 5vw;
    margin-top: 22px;

    @media (max-width: 800px) {
      width: 100%;
      top: 67px;
    }

    h2 {
      font-size: 4vw;
      font-weight: 900;
      line-height: 0.6;
      text-transform: uppercase;
      color: var(--black100);
      font-family: var(--mainKor-font);
      border-bottom: 0.4vw solid var(--black100);

      @media (max-width: 800px) {
        width: 100%;
        background-color: var(--mainBg-color);
        line-height: 1.8;
      }

      em {
        font-size: 1.25rem;
        font-weight: 400;
        line-height: 1.1;
      }
    }
  }
  .skill__desc {
    width: 50%;

    @media (max-width: 800px) {
      width: 100%;
    }
    span {
      font-size: 5vw;
      line-height: 1.3;
      font-weight: 900;
      font-family: var(--mainNum-font);

      @media (max-width: 800px) {
        margin-top: 50px;
        display: block;
        font-size: 9vw;
      }
    }

    h3 {
      font-size: 1.5rem;
      text-decoration: underline;
      text-underline-position: under;
      margin-bottom: 1vw;
    }

    p {
      margin-bottom: 30vh;
      font-size: 1.1rem;
      color: var(--black300);
      line-height: 1.7;

      @media (max-width: 800px) {
        margin-bottom: 20vh;
      }
    }
  }
}
</style>
