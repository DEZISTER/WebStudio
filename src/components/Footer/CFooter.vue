<template>
  <div class="footer">
    <main-container>
      <div class="footer__inner">
        <div class="footer__address">
          <e-logo :colorTheme="'dark'" />

          <address class="address">
            <ul class="address__list">
              <li class="address__item">
                <p class="address__element">м. Київ, пр-т Лесі Українки, 26</p>
              </li>
              <li class="address__item">
                <a class="address__link" href="mailto:info@devstudio.com"
                  >info@devstudio.com</a
                >
              </li>
              <li class="address__item">
                <a class="address__link" href="tel:+380961111111"
                  >+38 096 111 11 11</a
                >
              </li>
            </ul>
          </address>
        </div>

        <div class="footer__contacts">
          <p class="footer__sub-title">ПРИЄДНУЙТЕСЬ</p>
          <e-contact-list :contactList="contactList" :colorTheme="'dark'" />
        </div>

        <div class="footer__form">
          <p class="footer__sub-title">ПІДПИШІТЬСЯ НА РОЗСИЛКУ</p>

          <form class="subscribe-form">
            <main-input
              :typeInput="'email'"
              :colorTheme="'dark'"
              placeholder="E-mail"
              class="subscribe-form__input"
            />

            <main-button class="subscribe-form__button">
              <span>Підписатися</span>
              <svg
                class="subscribe-form__button-icon"
                width="24px"
                height="24px"
              >
                <use href="@/images/icons.svg#icon-icon-send"></use>
              </svg>
            </main-button>
          </form>
        </div>
      </div>
    </main-container>
  </div>
</template>

<script>
import MainContainer from "@/components/UI/MainContainer.vue";
import MainButton from "@/components/UI/MainButton.vue";
import EContactList from "../Elements/EContactList.vue";
import ELogo from "../Elements/ELogo.vue";
import MainInput from "../UI/MainInput.vue";
export default {
  components: { MainContainer, MainButton, EContactList, ELogo, MainInput },

  props: {
    contactList: {
      type: Array,
      required: true,
    },
    userEmail: {
      type: String,
    },
  },

  data() {
    return {}
  },
};
</script>

<style lang="scss" scoped>
.footer {
  padding: 60px 0;
  background-color: $first-bg-color;

  .logo {
    margin-bottom: 20px;
  }

  &__inner {
    @include display-position(space-between, center);
    flex-flow: column;
    color: $second-text-color;
    gap: 60px;
    text-align: center;
  }

  &__sub-title {
    padding-top: 10px;
    margin-bottom: 20px;
    text-transform: uppercase;
    @include font-styles(700, 14, 16);
  }

  &__contacts {
    width: 206px;
  }

  &__form {
    width: 100%;
  }

  @media screen and (min-width: 768px) {
    &__inner {
      gap: 60px 165px;
      flex-flow: row wrap;
      justify-content: center;
    }
  }

  @media screen and (min-width: 1200px) {
    &__inner {
      text-align: left;
    }
    &__inner {
      gap: 0;
      flex-flow: row;
      @include display-position(space-between, start);
    }
    &__form {
      width: auto;
    }
  }
}

.address {
  @include font-styles(400, 14, 24);

  &__item {
    margin-top: 9px;
  }

  &__link {
    color: rgba(255, 255, 255, 0.6);
    transition-property: color;
    transition-duration: 250ms;
    transition-timing-function: cubic-bezier(0.4, 0, 0.2, 1);

    &:hover,
    &:focus {
      color: $second-text-color;
    }
  }
}

.subscribe-form {
  @include display-position(space-between, center);
  flex-flow: column wrap;
  gap: 20px;

  &__input {
    width: 100%;
  }

  &__button {
    fill: $second-text-color;
  }

  &__button-icon {
    margin-left: 10px;
  }

  @media screen and (min-width: 480px) {
    &__input {
      width: 450px;
    }
  }

  @media screen and (min-width: 1200px) {
    flex-flow: row;
    gap: 12px;

    &__input {
      width: 358px;
    }
  }
}

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