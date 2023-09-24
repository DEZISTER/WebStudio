<template>
  <div class="app">
    <header>
      <c-nav />
      <c-header />
    </header>

    <main>
      <c-widgets :widgetsList="widgetsList" />
      <c-about-us :aboutUsList="aboutUsList" />
      <c-our-team :contactList="contactList" :teamList="teamList" />
      <c-our-clients :clientList="clientList" />
    </main>

    <footer>
      <c-footer :contactList="contactList" :userEmail="userEmail" />
    </footer>
  </div>
</template>

<script>
import CNav from "@/components/Header/CNav.vue";
import CHeader from "@/components/Header/CHeader.vue";
import CWidgets from "@/components/Main/CWidgets.vue";
import CAboutUs from "./components/Main/CAboutUs.vue";
import COurTeam from "./components/Main/COurTeam.vue";
import COurClients from "./components/Main/COurClients.vue";
import CFooter from "./components/Footer/CFooter.vue";
import EModalForm from './components/Elements/EModalForm.vue';

export default {
  components: {
    CNav,
    CHeader,
    CWidgets,
    CAboutUs,
    COurTeam,
    COurClients,
    CFooter,
    EModalForm,
  },

  data() {
    return {
      userEmail: "hello",
      widgetsList: [
        {
          key: 0,
          title: "Увага до деталей",
          description:
            "Ідейні міркування, і навіть початок повсякденної роботи з формування позиції.",
          iconName: "#icon-antenna",
        },
        {
          key: 1,
          title: "Пунктуальність",
          description:
            "Завдання організації, особливо рамки і місце навчання кадрів тягне у себе.",
          iconName: "#icon-clock",
        },
        {
          key: 2,
          title: "Планування",
          description:
            "Так само консультація з широким активом значною мірою зумовлює.",
          iconName: "#icon-diagram",
        },
        {
          key: 3,
          title: "Сучасні технології",
          description:
            "Значимість цих проблем настільки очевидна, що реалізація планових завдань.",
          iconName: "#icon-astronaut",
        },
      ],

      contactList: [
        {
          key: 0,
          name: "instagram",
          iconName: "#icon-instagram",
          link: "https://uk.wikipedia.org/wiki/Instagram",
        },
        {
          key: 1,
          name: "twitter",
          iconName: "#icon-twitter",
          link: "https://uk.wikipedia.org/wiki/Twitter",
        },
        {
          key: 2,
          name: "facebook",
          iconName: "#icon-facebook",
          link: "https://uk.wikipedia.org/wiki/Facebook",
        },
        {
          key: 3,
          name: "linkedin",
          iconName: "#icon-linkedin",
          link: "https://uk.wikipedia.org/wiki/LinkedIn",
        },
      ],

      aboutUsList: [
        {
          key: 0,
          title: "Десктопні додатки",
          image: {
            size_1x: require("@/images/box/box-1.jpg"),
            size_2x: require("@/images/box/box-1-2x.jpg"),
          },
        },
        {
          key: 1,
          title: "Мобільні додатки",
          image: {
            size_1x: require("@/images/box/box-2.jpg"),
            size_2x: require("@/images/box/box-2-2x.jpg"),
          },
        },
        {
          key: 2,
          title: "Дизайнерські рішення",
          image: {
            size_1x: require("@/images/box/box-3.jpg"),
            size_2x: require("@/images/box/box-3-2x.jpg"),
          },
        },
      ],

      clientList: [
        {
          key: 0,
          name: "client",
          iconName: "#icon-Logo-1",
          width: "41",
          height: "46.7",
        },
        {
          key: 1,
          name: "client",
          iconName: "#icon-Logo-2",
          width: "40",
          height: "52",
        },
        {
          key: 2,
          name: "client",
          iconName: "#icon-Logo-3",
          width: "43.46",
          height: "41.18",
        },
        {
          key: 3,
          name: "client",
          iconName: "#icon-Logo-4",
          width: "84.44",
          height: "40.62",
        },
        {
          key: 4,
          name: "client",
          iconName: "#icon-Logo-5",
          width: "62.54",
          height: "45.43",
        },
        {
          key: 5,
          name: "client",
          iconName: "#icon-Logo-6",
          width: "93.79",
          height: "43.93",
        },
      ],

      teamList: [
        {
          key: 0,
          name: "Ігор Дем'яненко",
          position: "Product Designer",
          contacts: [
            {
              key: 0,
              name: "instagram",
              iconName: "#icon-instagram",
              link: "https://uk.wikipedia.org/wiki/Instagram",
            },
            {
              key: 1,
              name: "twitter",
              iconName: "#icon-twitter",
              link: "https://uk.wikipedia.org/wiki/Twitter",
            },
            {
              key: 2,
              name: "facebook",
              iconName: "#icon-facebook",
              link: "https://uk.wikipedia.org/wiki/Facebook",
            },
            {
              key: 3,
              name: "linkedin",
              iconName: "#icon-linkedin",
              link: "https://uk.wikipedia.org/wiki/LinkedIn",
            },
          ],
          image: {
            mobile: {
              size_1x: require("@/images/team/mobile/image-1-mobile.jpg"),
              size_2x: require("@/images/team/mobile/image-1-mobile-2x.jpg"),
            },
            tablet: {
              size_1x: require("@/images/team/tablet/image-1-tablet.jpg"),
              size_2x: require("@/images/team/tablet/image-1-tablet-2x.jpg"),
            },
            desktop: {
              size_1x: require("@/images/team/desktop/image-1-desktop.jpg"),
              size_2x: require("@/images/team/desktop/image-1-desktop-2x.jpg"),
            },
          },
        },
        {
          key: 1,
          name: "Ольга Репіна",
          position: "Frontend Developer",
          contacts: [
            {
              key: 0,
              name: "instagram",
              iconName: "#icon-instagram",
              link: "https://uk.wikipedia.org/wiki/Instagram",
            },
            {
              key: 1,
              name: "twitter",
              iconName: "#icon-twitter",
              link: "https://uk.wikipedia.org/wiki/Twitter",
            },
            {
              key: 2,
              name: "facebook",
              iconName: "#icon-facebook",
              link: "https://uk.wikipedia.org/wiki/Facebook",
            },
            {
              key: 3,
              name: "linkedin",
              iconName: "#icon-linkedin",
              link: "https://uk.wikipedia.org/wiki/LinkedIn",
            },
          ],
          image: {
            mobile: {
              size_1x: require("@/images/team/mobile/image-2-mobile.jpg"),
              size_2x: require("@/images/team/mobile/image-2-mobile-2x.jpg"),
            },
            tablet: {
              size_1x: require("@/images/team/tablet/image-2-tablet.jpg"),
              size_2x: require("@/images/team/tablet/image-2-tablet-2x.jpg"),
            },
            desktop: {
              size_1x: require("@/images/team/desktop/image-2-desktop.jpg"),
              size_2x: require("@/images/team/desktop/image-2-desktop-2x.jpg"),
            },
          },
        },
        {
          key: 2,
          name: "Микола Тарасенко",
          position: "Marketing",
          contacts: [
            {
              key: 0,
              name: "instagram",
              iconName: "#icon-instagram",
              link: "https://uk.wikipedia.org/wiki/Instagram",
            },
            {
              key: 1,
              name: "twitter",
              iconName: "#icon-twitter",
              link: "https://uk.wikipedia.org/wiki/Twitter",
            },
            {
              key: 2,
              name: "facebook",
              iconName: "#icon-facebook",
              link: "https://uk.wikipedia.org/wiki/Facebook",
            },
            {
              key: 3,
              name: "linkedin",
              iconName: "#icon-linkedin",
              link: "https://uk.wikipedia.org/wiki/LinkedIn",
            },
          ],
          image: {
            mobile: {
              size_1x: require("@/images/team/mobile/image-3-mobile.jpg"),
              size_2x: require("@/images/team/mobile/image-3-mobile-2x.jpg"),
            },
            tablet: {
              size_1x: require("@/images/team/tablet/image-3-tablet.jpg"),
              size_2x: require("@/images/team/tablet/image-3-tablet-2x.jpg"),
            },
            desktop: {
              size_1x: require("@/images/team/desktop/image-3-desktop.jpg"),
              size_2x: require("@/images/team/desktop/image-3-desktop-2x.jpg"),
            },
          },
        },
        {
          key: 3,
          name: "Михайло Єрмаковський",
          position: "UI Designer",
          contacts: [
            {
              key: 0,
              name: "instagram",
              iconName: "#icon-instagram",
              link: "https://uk.wikipedia.org/wiki/Instagram",
            },
            {
              key: 1,
              name: "twitter",
              iconName: "#icon-twitter",
              link: "https://uk.wikipedia.org/wiki/Twitter",
            },
            {
              key: 2,
              name: "facebook",
              iconName: "#icon-facebook",
              link: "https://uk.wikipedia.org/wiki/Facebook",
            },
            {
              key: 3,
              name: "linkedin",
              iconName: "#icon-linkedin",
              link: "https://uk.wikipedia.org/wiki/LinkedIn",
            },
          ],
          image: {
            mobile: {
              size_1x: require("@/images/team/mobile/image-4-mobile.jpg"),
              size_2x: require("@/images/team/mobile/image-4-mobile-2x.jpg"),
            },
            tablet: {
              size_1x: require("@/images/team/tablet/image-4-tablet.jpg"),
              size_2x: require("@/images/team/tablet/image-4-tablet-2x.jpg"),
            },
            desktop: {
              size_1x: require("@/images/team/desktop/image-4-desktop.jpg"),
              size_2x: require("@/images/team/desktop/image-4-desktop-2x.jpg"),
            },
          },
        },
      ],
    };
  },
};
</script>

<style lang="scss">
@import "@/scss/base/_modern-normalize.scss";
@import "@/scss/base/_default-settings.scss";
footer {
  background: black;
}
</style>
