<template>
  <footer class="site-footer">
    <p class="site-footer__text">
      © Copyright NewsFetcher {{ currentYear() }}
      <a
        class="site-footer__link"
        href="https://i.pinimg.com/originals/dc/45/42/dc4542cb61c32bd20ca933a940f37451.jpg"
        target="_blank"
        rel="noopener noreferrer"
        >Heisenberg</a
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
$mrWhite: #fff;

.site-footer__link {
  color: $mrWhite;
  line-height: 2;
  text-decoration: none;
}
</style>
