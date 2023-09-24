<template>
  <a href="index.html" :class="colorTheme == 'dark' ? 'logo logo--dark' : 'logo'">
    <span class="logo__word">Web</span><span>Studio</span>
  </a>
</template>

<script>
export default {
    props: {
    colorTheme: {
      type: String
    },
  },
};
</script>

<style lang="scss" scoped>
.logo {
    @include font-styles(700, 24, 28);
    font-family: Raleway;
    color: $logo-light-theme;

    &--dark {
        color: $logo-dark-theme;
        &:hover, &:focus {
            color: $logo-dark-theme;
        }
    }

    &__word {
        color: $accent;
    }

    @media screen and (min-width: 480px) {
        .menu {
          display: none;
        }
    }
    @media screen and (min-width: 1200px) {
        @include font-styles(700, 26, 31);
    }
}
</style>