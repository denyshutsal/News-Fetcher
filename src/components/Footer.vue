<template>
  <footer class="site-footer">
    <p class="site-footer__text">
      © Copyright NewsFetcher {{ currentYear() }}
      <a
        class="site-footer__link"
        href="/"
        target="_blank"
        rel="noopener noreferrer"
        >DH</a
      >
    </p>
  </footer>
</template>

<script>
import { format } from "date-fns";

export default {
  methods: {
    currentYear() {
      return format(new Date(), "y");
    },
  },
};
</script>

<style lang="scss">
.site-footer__link {
  color: black;
  line-height: 2;
  text-decoration: none;
}
</style>
