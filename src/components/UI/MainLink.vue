<template>
  <a class="section-link"><slot></slot></a>
</template>

<script>
export default {
};
</script>

<style lang="scss" scoped>
.section-link {
  font-weight: 500;
    font-size: 18px;
    line-height: 35px;
    text-transform: uppercase;
    color: $mainAccent;

    &:hover, &:focus {
      text-decoration: underline;
      @include baseAnimation();
    }
}
</style>