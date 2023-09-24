<template>
  <div class="header-nav">
    <nav class="navigation">
      <main-container>
        <div class="navigation__inner">
          <div class="navigation__pages-container">
            <e-logo style="padding: 0" />

            <button
              class="menu-toggle js-open-menu"
              aria-expanded="false"
              aria-controls="mobile-menu"
              @click="openMobileMenu"
            >
              <svg class="close-icon" width="40px" height="40px">
                <use href="@/images/icons.svg#icon-burger-icon"></use>
              </svg>
            </button>

            <ul class="navigation__page-list menu">
              <li class="navigation__page-list-item">
                <a
                  href="index.html"
                  class="navigation__page-link navigation__page-link--active"
                  >Студія</a
                >
              </li>
              <li class="navigation__page-list-item">
                <a href="portfolio.html" class="navigation__page-link"
                  >Портфоліо</a
                >
              </li>
              <li class="navigation__page-list-item">
                <a href="#" class="navigation__page-link">Контакти</a>
              </li>
            </ul>
          </div>

          <ul class="navigation__contact-list menu">
            <li class="navigation__contact-list-item">
              <a href="#" class="navigation__contact-link">
                <svg class="navigation__icon mail" width="16px" height="12px">
                  <use href="@/images/icons.svg#icon-mail"></use>
                </svg>
                <span>info@devstudio.com</span>
              </a>
            </li>
            <li class="navigation__list-item">
              <a href="#" class="navigation__contact-link">
                <svg
                  class="navigation__icon telephone"
                  width="10px"
                  height="16px"
                >
                  <use href="@/images/icons.svg#icon-phone"></use>
                </svg>
                <span>+38 096 111 11 11</span>
              </a>
            </li>
          </ul>
        </div>
      </main-container>

      <div>
        <div :class="this.modileMenu ? 'mobile-menu is-open' : 'mobile-menu'">
          <main-container class="mobile-menu__container">
            <button
              class="mobile-menu__close menu-toggle"
              @click="closeMobileMenu"
            >
              <svg
                fill="currentColor"
                viewBox="0 0 20 20"
                xmlns="http://www.w3.org/2000/svg"
                width="24"
                height="24"
              >
                <path
                  fill-rule="evenodd"
                  d="M4.293 4.293a1 1 0 011.414 0L10 8.586l4.293-4.293a1 1 0 111.414 1.414L11.414 10l4.293 4.293a1 1 0 01-1.414 1.414L10 11.414l-4.293 4.293a1 1 0 01-1.414-1.414L8.586 10 4.293 5.707a1 1 0 010-1.414z"
                  clip-rule="evenodd"
                ></path>
              </svg>
            </button>

            <ul class="mobile-menu__pages">
              <li><a href="" class="link mobile-menu__link">About</a></li>
              <li><a href="" class="link mobile-menu__link">Products</a></li>
              <li><a href="" class="link mobile-menu__link">Contacts</a></li>
              <li><a href="" class="link mobile-menu__link">Career</a></li>
            </ul>
          </main-container>
        </div>
      </div>
    </nav>
  </div>
</template>

<script>
import MainContainer from "@/components/UI/MainContainer.vue";
import MainButton from "@/components/UI/MainButton.vue";
import ELogo from "../Elements/ELogo.vue";

export default {
  components: { MainContainer, MainButton, ELogo },

  data() {
    return {
      modileMenu: false,
    };
  },

  watch: {
    modileMenu: (modileMenu) => {
      document.body.style.overflow = modileMenu ? "hidden" : "auto";
    },
  },

  methods: {
    openMobileMenu() {
      this.modileMenu = true;
      console.log(this.modileMenu);
    },

    closeMobileMenu() {
      this.modileMenu = false;
      console.log(this.modileMenu);
    },
  },
};
</script>

<style lang="scss" scoped>
.navigation {
  border-bottom: 1px solid $header-border-bottom;

  &__inner {
    @include display-position(space-between, center);
  }

  &__pages-container {
    @include display-position(space-between, center);
    width: 100%;
  }

  &__page-list {
    @include display-position(space-between, center);
    width: 286px;
    color: $main-text-color;
    padding-left: 93px;
  }

  &__contact-list {
    @include display-position(space-between, center);
    gap: 30px;
    color: $description-text-color;
  }

  &__page-link {
    @include font-styles(500, 14, 16, 0.02em);
    padding: 32px 0;
    position: relative;
    transition-property: color, fill;
    transition-duration: 250ms;
    transition-timing-function: cubic-bezier(0.4, 0, 0.2, 1);

    &:hover,
    &:focus {
      color: $accent;
      fill: $accent;
    }

    &--active {
      color: $accent;
      &::after {
        content: "";
        position: absolute;
        left: 0;
        bottom: -1px;
        width: 100%;
        height: 4px;
        background: #2196f3;
        border-radius: 2px;
      }
    }
  }

  &__page-list-item {
    &:nth-child(1) {
      margin-right: 53px;
    }

    &:nth-child(2) {
      margin-right: 50px;
    }
  }

  &__contact-link {
    @extend .navigation__page-link;
    color: $description-text-color;
    @include display-position(space-between, center);
  }

  &__icon {
    margin-right: 10px;
  }

  .menu {
    display: none;
  }

  .mobile-menu {
    position: absolute;
    height: 100vh;
    background: #2196f3;
    top: 0;
    left: 0;
    width: 100%;
    display: none;

    transform: translateX(100%);
    transition: transform 250ms ease-in-out;

    &__container {
      position: relative;
      margin-top: 10px;
    }

    &__close {
      right: 15px;
      width: 40px;
      height: 40px;
      position: absolute;

      &:hover,
      &:focus {
        color: white;
      }
    }

    &__pages {
      display: flex;
      flex-flow: column;
      gap: 20px;
      width: 100%;
      min-height: 100vh;
      justify-content: center;
      align-items: center;
      font-size: 40px;
    }

    &__link {
      &:hover,
      &:focus {
        color: white;
      }
    }
  }

  .mobile-menu.is-open {
    transform: translateX(0);
    display: flex;
  }

  @media screen and (min-width: 480px) {
  }

  @media screen and (min-width: 768px) {
    .menu {
      display: flex;
    }
    .menu-toggle {
      display: none;
    }
    &__contact-list {
      flex-flow: column;
      align-items: flex-start;
      padding: 21px 0;
      gap: 10px;
    }
    &__contact-link {
      padding: 0;
      @include font-styles(500, 12, 14, 0.02em);
    }
    .telephone {
      width: 10px;
      height: 14px;
    }
    .mail {
      width: 14px;
      height: 10px;
    }
    &__pages-container {
      justify-content: left;
    }
  }

  @media screen and (min-width: 1200px) {
    &__pages-container {
      width: auto;
    }
    &__page-list {
      width: 286px;
      padding-left: 93px;
    }

    &__contact-list {
      @include display-position(space-between, center);
      flex-flow: row;
      gap: 30px;
      padding: 0;
    }

    &__page-link {
      @include font-styles(500, 14, 16, 0.02em);
      padding: 32px 0;
    }
  }
}
</style>