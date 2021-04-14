<template>
  <section class="news-card">
    <div class="news-card__header">
      <a
        class="news-card__title"
        :href="post.url"
        target="_blank"
        rel="noreferrer"
      >
        {{ post.title }}
      </a>
      <img class="news-card__img" :src="post.thumbnail" :alt="post.caption" />
      <p class="news-card__text">
        {{ post.abstract }}
      </p>
    </div>
    <div class="news-card__footer">
      <p class="news-card__author">{{ post.byline }}</p>
      <p class="news-card__date">
        {{ formatDate(post.published_date) }}
      </p>
    </div>
  </section>
</template>

<script>
import { format } from "date-fns";

export default {
  props: {
    post: {
      type: Object,
      required: true,
    },
  },
  methods: {
    formatDate(strDate) {
      return format(new Date(strDate), "MMMM do, yyyy");
    },
  },
};
</script>

<style lang="scss">
%fontStyles {
  font-size: 0.9rem;
  font-weight: 700;
  margin: 0;
}

.news-card {
  display: flex;
  flex-direction: column;
  justify-content: space-between;
  padding: 1rem;
  text-align: left;
  background-color: #fafafa;
  border-radius: 5px;
  box-shadow: 0 3px 6px rgb(0 0 0 / 16%), 0 3px 6px rgb(0 0 0 / 23%);

  &__header {
    margin-bottom: 1rem;
  }

  &__title {
    display: inline-block;
    margin-bottom: 1rem;
    font-size: 1.2rem;
    font-weight: 700;
    line-height: 1.3;
    color: inherit;
    text-decoration: none;
  }

  &__img {
    display: block;
    width: 100%;
    height: auto;
    margin-bottom: 1rem;
  }

  &__text {
    margin: 0;
    line-height: 1.5;
  }

  &__author,
  &__date {
    @extend %fontStyles;
  }

  &__author {
    margin-bottom: 0.5rem;
  }
}
</style>
