<template>
  <section class="widgets">
    <main-container>
      <section-title class="widgets__title" hidden
        >Коротко про нас</section-title
      >

      <ul class="widgets__list">
        <li class="widgets__item" :key="widgetsItem" v-for="widgetsItem in widgetsList">
          <div class="widgets__item-preview">
            <svg class="widgets__item-icon" width="70px" height="70px">
              <use :xlink:href="require('@/images/icons.svg') + widgetsItem.iconName"></use>
            </svg>
          </div>
          <h4 class="widgets__item-title">{{widgetsItem.title.toUpperCase()}}</h4>
          <p class="widgets__item-description">
            {{widgetsItem.description}}
          </p>
        </li>
      </ul>
    </main-container>
  </section>
</template>

<script>
import SectionTitle from "../UI/SectionTitle.vue";
import MainContainer from "../UI/MainContainer.vue";

export default {
  components: { SectionTitle, MainContainer },

  props: {
    widgetsList: {
      type: Array,
      required: true,
    }
  }
};
</script>

<style lang="scss" scoped>
.widgets {
  padding: 60px 0;

  &__list {
    flex-flow: column;
    @include display-position(space-between, start);
    gap: 30px;
  }

  &__item {
    width: 100%;
  }

  &__item-preview {
    padding: 25px 0;
    margin-bottom: 30px;
    @include display-position(center, center);
    background: $second-bg-color;
    border-radius: 4px;
  }

  &__item-title {
    text-transform: uppercase;
    @include font-styles(700, 14, 16);
    margin-bottom: 10px;
    text-align: center;
  }

  &__item-description {
    @include font-styles(null, 14, 24);
    color: $description-text-color;
  }

  @media screen and (min-width: 768px) {
    padding: 94px 0;
    &__item-title {
      text-align: left;
    }
    &__list {
      flex-flow: row wrap;
    }
    &__item {
      width: calc((100% - 30px) / 2);
    }
  }

  @media screen and (min-width: 1200px) {
    padding: 94px 0;
    &__list {
      flex-flow: row nowrap;
    }
    &__item {
      width: calc((100% - 90px) / 4);
    }
  }
}
</style>