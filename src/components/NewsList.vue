<template>
  <div class="news-list">
    <NewsCard v-for="(post, index) in posts" :key="index" :post="post" />
  </div>
</template>

<script>
import NewsCard from "./NewsCard.vue";
export default {
  props: {
    posts: {
      type: Array,
      required: true,
    },
  },
  components: {
    NewsCard,
  },
};
</script>

<style lang="scss">
.news-list {
  display: grid;
  justify-items: center;
  gap: 1.5rem;
  grid-template-columns: 18rem;
  margin-top: 3rem;

  @media (min-width: 768px) {
    grid-template-columns: repeat(2, 18rem);
  }

  @media (min-width: 1024px) {
    grid-template-columns: repeat(3, 18rem);
  }

  @media (min-width: 1536px) {
    grid-template-columns: repeat(4, 18rem);
  }
}
</style>
