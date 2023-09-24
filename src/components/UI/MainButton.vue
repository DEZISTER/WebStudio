<template>
  <button class="main-button">
    <slot></slot>
  </button>
</template>

<script>
export default {};
</script>

<style lang="scss" scoped>
.main-button {
    background-color: $accent;
    border: none;
    min-width: 200px;
    color: $button-text;
    padding: 10px 0;
    display: flex;
    align-items: center;
    text-align: center;
    @include display-position(center, center);
    @include font-styles(700, 16, 30, 0.06em);
    box-shadow: 0px 4px 4px rgba(0, 0, 0, 0.15);
    border-radius: 4px;
    transition-property: background-color, fill;
    transition-duration: 250ms;
    transition-timing-function: cubic-bezier(0.4, 0, 0.2, 1);
    margin: auto;

    &:hover, &:focus {
        background-color: $button-active;
    }
}
</style>