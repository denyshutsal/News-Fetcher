<template>
  <Header />
  <main class="site-main">
    <slot />
  </main>
  <Footer />
</template>

<script>
import Header from "./Header.vue";
import Footer from "./Footer.vue";

export default {
  components: {
    Header,
    Footer,
  },
};
</script>

<style lang="scss">
.site-main {
  display: flex;
  flex-direction: column;
  justify-content: center;
  align-items: center;
  width: 100%;
  max-width: 1500px;
  margin: 0 auto;
  padding: 30px 10px;

  &__title {
    font-size: 1.8rem;
    line-height: 1.4;
    margin-top: 0;
    margin-bottom: 1rem;
    color: #bdbdbd;
  }

  &__span {
    text-transform: capitalize;
    color: #546e7a;
  }
}
</style>
