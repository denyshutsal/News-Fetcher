<template>
  <div class="news-filter">
    <!-- Start of select dropdown -->
    <div class="news-filter__select-wrapper select-block">
      <label for="news-filter-select" class="select-block__label sr-only"
        >News Select</label
      >
      <select
        id="news-filter-select"
        class="select-block__select"
        v-model="section"
      >
        <option
          class="select-block__option"
          v-for="(section, index) in sections"
          :key="index"
          :value="section"
        >
          {{ section }}
        </option>
      </select>
    </div>
    <!-- End of select dropdown -->
    <div class="news-filter__button-wrapper">
      <button class="news-filter__button btn" @click="fetch">Show</button>
    </div>
  </div>
</template>

<script>
import { computed } from "vue";
import sectionsData from "./sections";

export default {
  props: {
    modelValue: String,
    fetch: Function,
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
};
</script>

<style lang="scss">
$btnColor: #fff;
$btnBgColor: #546e7a;

%outline-styles {
  outline-style: solid;
  outline-color: transparent;
  box-shadow: 0 0 0 4px scale-color($btnBgColor, $lightness: -40%);
}

.select-block {
  width: 100%;
  border: 1px solid #777;
  border-radius: 0.25em;
  margin-bottom: 1rem;
  padding: 0.25em 0.5em;
  font-size: 1.25rem;
  cursor: pointer;
  line-height: 1.1;
  background-color: #fff;
  background-image: linear-gradient(to top, #f9f9f9, #fff 33%);

  &:focus-within {
    @extend %outline-styles;
  }

  &__select {
    // Resets for further consistency
    background-color: transparent;
    border: none;
    padding: 0 1em 0 0;
    margin: 0;
    width: 100%;
    font-family: inherit;
    font-size: 1rem;
    cursor: inherit;
    line-height: inherit;
    outline: none;
  }

  &__option {
    text-transform: capitalize;
  }
}

.news-filter {
  &__button {
    display: inline-flex;
    align-items: center;
    justify-content: center;
    font-size: 1rem;
    background-color: $btnBgColor;
    color: $btnColor;
    border-radius: 8px;
    box-shadow: 0 3px 5px rgba(0, 0, 0, 0.18);
    padding: 0.25em 0.75em;
    min-width: 10ch;
    min-height: 44px;
    text-align: center;
    line-height: 1.1;
    transition: 220ms all ease-in-out;

    &:hover,
    &:active {
      color: scale-color($btnColor, $lightness: -20%);
      background-color: scale-color($btnBgColor, $lightness: -20%);
    }

    &:focus {
      color: scale-color($btnColor, $lightness: -20%);
      @extend %outline-styles;
    }
  }
}
</style>
