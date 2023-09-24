<template>
  <section class="our-team">
    <main-container>
      <section-title class="our-team__title">Наша команда</section-title>

      <ul class="our-team__list">
        <li class="our-team__item team-card" :key="developer.key" v-for="developer in teamList" :name="teamList.indexOf(developer)">
          <picture>
            <source
              :srcset="developer.image.desktop.size_1x + ' 1x, ' + developer.image.desktop.size_2x + ' 2x'"
              media="(min-width: 1200px)"
            />
            <source
              :srcset="developer.image.tablet.size_1x + ' 1x, ' + developer.image.tablet.size_2x + ' 2x'"
              media="(min-width: 768px)"
            />
            <img
              class="team-card__image"
              :srcset="developer.image.mobile.size_1x + ' 1x, ' + developer.image.mobile.size_2x + ' 2x'"
              :src="developer.image.mobile.size_1x"
              :alt="developer.name"
              width="100%"
            />
          </picture>

          <div class="team-card__context">
            <h3 class="team-card__title">{{developer.name}}</h3>
            <p class="team-card__description">{{developer.position}}</p>
            <e-contact-list :contactList="developer.contacts" />
          </div>
        </li>
      </ul>
    </main-container>
  </section>
</template>

<script>
import SectionTitle from "../UI/SectionTitle.vue";
import MainContainer from "../UI/MainContainer.vue";
import EContactList from "../Elements/EContactList.vue";

export default {
  components: { SectionTitle, MainContainer, EContactList },
  props: {
    contactList: {
      type: Array,
      required: true,
    },
    teamList: {
      type: Array,
      required: true,
    },
  },

  methods: {},

  // created() {
  //   console.log(this.teamList[3].image.mobile.size_1x);
  // }
};
</script>

<style lang="scss" scoped>
.our-team {
  padding: 60px 0;
  background: $second-bg-color;

  @media screen and (min-width: 1200px) {
    padding: 94px 0;
  }

  &__list {
    display: flex;
    flex-flow: column;
    gap: 30px;

    @media screen and (min-width: 768px) {
      flex-flow: row wrap;
    }

    @media screen and (min-width: 1200px) {
    }
  }
}

.team-card {
  width: 100%;
  background-color: $page-bg-color;
  box-shadow: 0px 1px 3px rgba(0, 0, 0, 0.12), 0px 1px 1px rgba(0, 0, 0, 0.14),
    0px 2px 1px rgba(0, 0, 0, 0.2);
  border-radius: 0px 0px 4px 4px;

  &__context {
    width: 206px;
    padding: 30px 0 24px;
    margin: auto;
  }

  &__title {
    text-align: center;
    @include font-styles(500, 16, 19);
    margin-bottom: 10px;
  }

  &__description {
    text-align: center;
    color: $description-text-color;
    @include font-styles(null, 16, 19);
    margin-bottom: 16px;
  }

  &__image {
    width: 100%;
  }

  @media screen and (min-width: 768px) {
    width: calc((100% - 30px) / 2);
    &__context {
      width: 206px;
      padding: 30px 0 24px;
      margin: auto;
    }
  }

  @media screen and (min-width: 1200px) {
    width: calc((100% - 90px) / 4);
    &__context {
      padding: 30px 0;
    }
  }
}
</style>