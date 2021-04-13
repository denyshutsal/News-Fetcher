<template>
  <div class="news-filter">
    <!-- Start of select dropdown -->
    <div class="news-filter__select-wrapper select-block">
      <select class="select-block__select" v-model="section">
        <option
          v-for="(section, index) in sections"
          :key="index"
          :value="section"
        >
          {{ capitalize(section) }}
        </option>
      </select>
    </div>
    <!-- End of select dropdown -->
    <div class="news-filter__button-wrapper">
      <button class="news-filter__button btn">Retrieve</button>
    </div>
  </div>
</template>

<script>
import { computed } from "vue";
import sectionsData from "./sections";

export default {
  props: {
    modelValue: String,
  },
  setup(props, { emit }) {
    const section = computed({
      get: () => props.modelValue,
      set: (value) => emit("update:modelValue", value),
    });

    return {
      section,
    };
  },
  data() {
    return {
      sections: sectionsData,
    };
  },
  methods: {
    capitalize(value) {
      if (!value) return "";
      value = value.toString();
      return value.charAt(0).toUpperCase() + value.slice(1);
    },
  },
};
</script>
