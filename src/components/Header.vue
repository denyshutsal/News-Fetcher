<template>
  <header class="site-header">
    <img
      class="site-header__logo"
      src="../assets/site_logo.png"
      alt="site-header__logo"
      width="32"
    />
    <span class="site-header__text">News Fetcher</span>
  </header>
</template>

<style lang="scss">
.site-header {
  display: flex;
  flex-direction: row;
  justify-content: flex-start;
  align-items: center;
  background-color: wheat;

  &__logo {
    width: 32px;
    margin: 0.5rem;
  }

  &__text {
    font-size: 1.2rem;
  }
}
</style>
