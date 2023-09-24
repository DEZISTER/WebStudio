<template>
  <div
    :class="modalState ? 'backdrop' : 'backdrop is-hidden'"
    @click="dataModalClose"
  >
    <div class="modal" @click.stop>
      <button class="modal-close-button" @click="dataModalClose">
        <svg class="close-icon" width="18px" height="18px">
          <use href="@/images/icons.svg#icon-close"></use>
        </svg>
      </button>

      <form class="modal-form">
        <h3 class="form-title">Залиште свої дані, ми вам передзвонимо</h3>

        <label class="modal-label" for="name">Ім'я</label>
        <div class="modal-wrap">
          <input
            class="modal-input"
            type="text"
            name="name"
            id="name"
            placeholder=""
            required
          />
          <svg class="modal-icon" width="18px" height="18px">
            <use href="@/images/icons.svg#icon-person-form"></use>
          </svg>
        </div>

        <label class="modal-label" for="phone">Телефон</label>
        <div class="modal-wrap">
          <input
            class="modal-input"
            type="tel"
            name="phone"
            id="phone"
            placeholder=""
            required
          />
          <svg class="modal-icon" width="18px" height="18px">
            <use href="@/images/icons.svg#icon-contact-form"></use>
          </svg>
        </div>

        <label class="modal-label" for="email">Пошта</label>
        <div class="modal-wrap">
          <input
            class="modal-input"
            type="email"
            name="email"
            id="email"
            placeholder=""
            required
          />
          <svg class="modal-icon" width="18px" height="18px">
            <use href="@/images/icons.svg#icon-email-form"></use>
          </svg>
        </div>

        <label class="modal-label" for="comment">Коментар</label>
        <div class="modal-wrap">
          <textarea
            class="modal-input modal-area"
            type="password"
            name="comment"
            id="comment"
            placeholder="Введіть текст"
          ></textarea>
        </div>

        <div class="modal-checker">
          <input
            type="checkbox"
            id="scales"
            name="scales"
            class="custom-checkbox"
            checked
          />
          <label for="scales"
            ><p class="confirmation">
              Погоджуюся з розсилкою та приймаю&nbsp;<a
                href="/"
                class="default-link"
                >Умови договору</a
              >
            </p></label
          >
        </div>

        <div class="button">
          <button class="confirm" @click="dataModalClose">Відправити</button>
        </div>
      </form>
    </div>
  </div>
</template>

<script>
export default {
  props: {
    modalState: {
      type: Boolean,
      required: true,
    },
  },

  watch: {
    modalState: (modalState) => {
      document.body.style.overflow = modalState ? "hidden" : "auto";
    },
  },

  methods: {
    dataModalClose() {
      this.$emit("setModalState", false);
    },
  },
};
</script>

<style lang="scss" scoped>
.is-hidden {
  visibility: hidden;
  opacity: 0;
}

.backdrop {
  position: fixed;
  left: 0;
  top: 0;
  width: 100%;
  height: 100vh;
  background: rgba(0, 0, 0, 0.2);
  z-index: 1;
  transition-duration: 250ms;
  transition-property: opacity, visibility;
  transition-timing-function: cubic-bezier(0.4, 0, 0.2, 1);
}

.modal {
  width: 528px;
  height: 581px;
  position: absolute;
  bottom: 0;
  left: 0;
  right: 0;
  top: 0;
  margin: auto;
  background: #ffffff;
  box-shadow: 0 1px 3px rgba(0, 0, 0, 0.12), 0 1px 1px rgba(0, 0, 0, 0.14),
    0 2px 1px rgba(0, 0, 0, 0.2);
  border-radius: 4px;
}

.modal-close-button {
  display: flex;
  justify-content: center;
  align-items: center;
  position: absolute;
  right: 8px;
  top: 8px;
  height: 30px;
  width: 30px;
  background: #ffffff;
  border: 1px solid rgba(0, 0, 0, 0.1);
  border-radius: 30px;
}

.close-icon,
.modal-icon {
  transition-duration: 250ms;
  transition-property: fill;
  transition-timing-function: cubic-bezier(0.4, 0, 0.2, 1);
}

.modal-close-button:hover .close-icon,
.modal-close-button:focus .close-icon {
  fill: #2196f3;
}

.modal-wrap:hover .modal-icon,
.modal-wrap:focus .modal-icon {
  fill: #2196f3;
}

.form-title {
  font-weight: 700;
  font-size: 20px;
  line-height: 1.15;
  text-align: center;
  letter-spacing: 0.03em;
  color: #212121;
  margin-bottom: 2px;
}

.modal-form {
  margin: 40px;
  text-align: left;
  font-size: 12px;
  line-height: 1.17;
  letter-spacing: 0.01em;
}

.modal-label {
  display: inline-block;
  margin: 10px 0 4px;
  color: #757575;
}

.modal-input {
  width: 100%;
  height: 40px;
  border: 1px solid rgba(33, 33, 33, 0.2);
  border-radius: 4px;
  outline: transparent;
  padding-left: 42px;
  transition-duration: 250ms;
  transition-property: border;
  transition-timing-function: cubic-bezier(0.4, 0, 0.2, 1);
}

.modal-wrap {
  position: relative;
  display: flex;
  align-items: center;
}

.modal-icon {
  position: absolute;
  left: 12px;
}

.modal-area {
  padding: 12px 16px;
  height: 120px;
  resize: none;
}

.default-link {
  color: #2196f3;
  text-decoration: underline;
}

.modal-checker {
  margin: 20px auto 30px;
  text-align: center;
}

.modal-checker label p {
  font-size: 14px;
  line-height: 1.7;
  letter-spacing: 0.03em;
  display: flex;
}

.custom-checkbox {
  position: absolute;
  z-index: -1;
  opacity: 0;
}

.custom-checkbox + label {
  display: inline-flex;
  align-items: center;
  user-select: none;
}

.custom-checkbox + label::before {
  content: "";
  display: inline-block;
  width: 16px;
  height: 15px;
  flex-shrink: 0;
  flex-grow: 0;
  border: 1px solid rgba(33, 33, 33, 0.2);
  border-radius: 2px;
  margin-right: 7px;
  background-repeat: no-repeat;
  background-position: center center;
}

.custom-checkbox:checked + label::before {
  border-color: #0b76ef;
  background-color: #0b76ef;
  background-image: url("@/images/check.svg");
}

.confirm {
  width: 200px;
  height: 50px;
  margin: auto;
  background: #188ce8;
  box-shadow: 0 4px 4px rgba(0, 0, 0, 0.15);
  border-radius: 4px;
  color: #eeeeee;
  border: none;
  font-weight: 700;
  font-size: 16px;
  line-height: 30px;
  letter-spacing: 0.06em;
}
</style>