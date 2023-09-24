<template>
  <input
    :type="typeInput"
    :value="modelValue"
    @input="updateInput"
    :class="colorTheme == 'dark' ? 'main-input main-input--dark' : 'main-input'"
  />
</template>

<script>
export default {
  name: "main-input",
  props: {
    modelValue: [String, Number],
    typeInput: {
      type: String,
      required: true,
    },
    colorTheme: {
        type: String,
    }
  },

  methods: {
    updateInput(event) {
      this.$emit("update:modelValue", event.target.value);
    },
  },
};
</script>

<style scoped  lang="scss">
.main-input {
  border: 1px solid rgba(255, 255, 255, 0.3);
  filter: drop-shadow(0px 4px 4px rgba(0, 0, 0, 0.15));
  border-radius: 4px;
  color: rgba(255, 255, 255, 0.6);
  background: rgba(0, 0, 0, 0);
  width: 100%;
  height: 50px;
  padding: 15px 16px;
  outline: none;
  transition-property: color, border, fill;
  transition-duration: 250ms;
  transition-timing-function: cubic-bezier(0.4, 0, 0.2, 1);
  @include font-styles(400, 16, 20);

  &:hover,
  &:focus {
    border: 1px solid $accent;
    color: $dark-text;
  }

  &--dark {
    color: $second-text-color;

    &:hover,
    &:focus {
      color: $second-text-color;
    }
  }
}
</style>