<template>
  <div class="header-main">
    <section class="main-screen">
      <main-container>

        <h1 class="main-screen__title">
          Ефективні рішення для вашого&nbsp;бізнесу
        </h1>

        <main-button
          type="button"
          class="main-screen__button main-button"
          @click="this.modalState = true"
        >
          Замовити послугу
        </main-button>

        <e-modal-form :modalState="this.modalState" @setModalState="(event) => this.modalState = event"></e-modal-form>

      </main-container>
    </section>
  </div>
</template>

<script>
import MainContainer from "@/components/UI/MainContainer.vue";
import MainButton from "@/components/UI/MainButton.vue";
import EModalForm from "@/components/Elements/EModalForm.vue";
export default {
  components: { MainContainer, MainButton, EModalForm },

  data() {
    return {
      modalState: false,
    }
  }
};
</script>

<style lang="scss" scoped>
.main-screen {
    background: linear-gradient(rgba(47, 48, 58, 0.4), rgba(47, 48, 58, 0.4)), url('../../images/bg-main/bg-main-section-mobile.jpg') no-repeat center;
    background-size: cover;
    padding: 118px 0;

    @media (min-device-pixel-ratio: 2),
    (min-resolution: 192dpi),
    (min-resolution: 2dppx) {
        background: linear-gradient(rgba(47, 48, 58, 0.4), rgba(47, 48, 58, 0.4)), url('../../images/bg-main/bg-main-section-mobile-2x.jpg') no-repeat center;
        background-size: cover;
    }

    &__title {
        color: $second-text-color;
        text-transform: uppercase;
        text-align: center;
        margin: auto auto 30px;
        @include font-styles(900, 26, 42, 0.06em);
    }

    &__button {
        width: 200px;
        padding: 10px 0;
    }

    @media screen and (min-width: 768px) {
        background: linear-gradient(rgba(47, 48, 58, 0.4), rgba(47, 48, 58, 0.4)), url('../../images/bg-main/bg-main-section-tablet.jpg') no-repeat center;
        background-size: cover;

        @media (min-device-pixel-ratio: 2),
        (min-resolution: 192dpi),
        (min-resolution: 2dppx) {
            background: linear-gradient(rgba(47, 48, 58, 0.4), rgba(47, 48, 58, 0.4)), url('../../images/bg-main/bg-main-section-tablet-2x.jpg') no-repeat center;
            background-size: cover;
        }

        &__title {
            width: 360px;
        }
    }

    @media screen and (min-width: 1200px) {
        background: linear-gradient(rgba(47, 48, 58, 0.4), rgba(47, 48, 58, 0.4)), url('../../images/bg-main/bg-main-section.jpg') no-repeat center;
        background-size: cover;

        @media (min-device-pixel-ratio: 2),
        (min-resolution: 192dpi),
        (min-resolution: 2dppx) {
            background: linear-gradient(rgba(47, 48, 58, 0.4), rgba(47, 48, 58, 0.4)), url('../../images/bg-main/bg-main-section-2x.jpg') no-repeat center;
            background-size: cover;

        }

        padding: 200px 0;

        &__title {
            width: 696px;
        }

        &__title {
            @include font-styles(900, 44, 60, 0.06em);
            line-height: 60px;
        }

        &__button {
            width: 216px;
        }
    }
}
</style>