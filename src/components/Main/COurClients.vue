<template>
  <section class="our-clients">
    <main-container>
      <section-title class="our-clients__title">Постійні клієнти</section-title>

      <ul class="our-clients__list clients-list">
        <li class="clients-list__item" :key="clientItem.key" v-for="clientItem in clientList">
          <a href="#" class="clients-list__link">
            <svg class="clients-list__icon" :width="clientItem.width" :height="clientItem.height">
              <use :xlink:href="require('@/images/icons.svg') + clientItem.iconName"></use>
            </svg>
          </a>
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
    clientList: {
      type: Array,
      required: true,
    }
  },
};
</script>

<style lang="scss" 
SectionTitlescoped>
.our-clients {
    padding: 60px 0;

    @media screen and (min-width: 1200px) {
        padding: 94px 0;
    }
}

.clients-list {
    @include display-position(space-between, center);
    flex-flow: wrap;
    gap: 30px;

    &__item {
        width: 100%;
    }

    &__link {
        @include display-position(center, center);
        width: 100%;
        height: 92px;
        border: 1px solid $unactive-icon;
        fill: $unactive-icon;
        border-radius: 4px;
        transition-property: border-color, fill;
        transition-duration: 250ms;
        transition-timing-function: cubic-bezier(0.4, 0, 0.2, 1);

        &:hover, &:focus {
            fill: $active-bg-icon;
            border-color: $active-bg-icon;
        }
    }

    @media screen and (min-width: 480px) {
        &__item {
            width: calc((100% - 30px) / 2);
        }
    }

    @media screen and (min-width: 768px) {
        &__item {
            width: calc((100% - 60px) / 3);
        }
    }

    @media screen and (min-width: 1200px) {
        &__item {
            width: calc((100% - 150px) / 6);
        }
    }
}
</style>