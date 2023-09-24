<template>
  <section class="about-us">
    <main-container>
      <section-title class="about-us__title">Чим ми займаємося</section-title>

      <ul class="about-us__list work-list">
        <li class="work-list__item" :key="aboutUsItem.key" v-for="aboutUsItem in aboutUsList">
          <img
            class="work-list__image"
            :srcset="aboutUsItem.image.size_1x + ' 1x, ' + aboutUsItem.image.size_2x + ' 2x'"
            :src="aboutUsItem.image.size_1x"
            alt="Box 1"
            width="370"
          />
          <p class="work-list__description">{{aboutUsItem.title}}</p>
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
    aboutUsList: {
      type: Array,
      required: true,
    },
  },

  methods: {},

//   created() {
//     console.log(this.aboutUsList);
//   }
};
</script>

<style lang="scss" scoped>
.about-us {
  display: none;
  padding: 0 0 94px;

  @media screen and (min-width: 1200px) {
    display: block;
  }
}

.work-list {
  @include display-position(space-between, start);

  &__item {
    position: relative;
  }

  &__description {
    width: 100%;
    position: absolute;
    bottom: 0;
    text-align: center;
    text-transform: uppercase;
    color: $second-text-color;
    @include font-styles(700, 14, 16);
    background: rgba(47, 48, 58, 0.8);
    padding: 27px;
  }
}
</style>