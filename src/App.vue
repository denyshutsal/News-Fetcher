<template>
  <Layout>
    <h1 class="site-main__title">
      News Section: <span class="site-main__span">{{ section }}</span>
    </h1>
    <NewsFilter v-model="section" />
    <NewsList :posts="posts" />
  </Layout>
</template>

<script>
import Layout from "./components/Layout.vue";
import NewsFilter from "./components/NewsFilter.vue";
import NewsList from "./components/NewsList.vue";

import data from "./posts.json";

export default {
  components: {
    Layout,
    NewsFilter,
    NewsList,
  },
  data() {
    return {
      section: "home",
      posts: data.posts,
    };
  },
};
</script>

<style lang="scss">
#app {
  font-family: Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
}
</style>
