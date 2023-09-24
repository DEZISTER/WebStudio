<template>
  <ul class="contact-list">
    <li
      class="contact-list__item"
      :key="contactItem.key"
      v-for="contactItem in contactList"
    >
      <a :href="contactItem.link" :class="colorTheme == 'dark' ? 'contact-list__link contact-list__link--dark' : 'contact-list__link'">
        <svg class="contact-list__icon" width="20px" height="20px">
          <use
            :xlink:href="require('@/images/icons.svg') + contactItem.iconName"
          ></use>
        </svg>
      </a>
    </li>
  </ul>
</template>

<script>
export default {
  props: {
    contactList: {
      type: Array,
      required: true,
    },
    colorTheme: {
      type: String
    },
  },
};
</script>

<style lang="scss" scoped>
.contact-list {
  @include display-position(space-between, center);

  &__link {
    padding: 12px;
    @include display-position(center, center);
    width: 44px;
    fill: $unactive-icon;
    background: none;
    border-radius: 44px;
    transition-property: background-color, fill;
    transition-duration: 250ms;
    transition-timing-function: cubic-bezier(0.4, 0, 0.2, 1);

    &--dark {
      background: rgba(255, 255, 255, 0.1);
      fill: $active-icon;
    }

    &:hover,
    &:focus {
      background-color: $active-bg-icon;
      fill: $active-icon;
    }
  }
}
</style>