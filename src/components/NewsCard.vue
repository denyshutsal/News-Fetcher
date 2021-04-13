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
      <img
        class="news-card__img"
        :src="post.thumbnail"
        :alt="post.caption"
        height="140"
        width="210"
      />
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
