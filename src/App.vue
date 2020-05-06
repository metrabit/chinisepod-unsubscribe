<template>
  <div id="app">
    <Header />
    <section class="d-flex unsubscribe-info">
      <h2 class="unsubscribe-info__title">Unsubscribe</h2>
      <div class="d-flex unsubscribe-info__content">
        <iframe
          src="https://www.youtube.com/embed/tgbNymZ7vqY"
          height="280px"
          class="unsubscribe-info__video"
        ></iframe>
        <div class="unsubscribe-info__feedback">
          <p class="unsubscribe-info__feedback-title">Please tell us WHY you are unsubscribing:</p>
          <textarea placeholder="please tell us why you are unsubscribing"></textarea>
        </div>
      </div>
    </section>
    <section class="d-flex unsubscribe-form">
      <div>
        <div class="unsubscribe-form__all">
          <h3 class="unsubscribe-form__all-title">What emails do you want to unsubscribe from?</h3>
          <Checkbox label="All emails" class="ml-2" id="allEmails" />
        </div>
        <div class="unsubscribe-form__select">
          <h3 class="unsubscribe-form__select-title">OR: Please select your preferences:</h3>
          <div class="d-flex unsubscribe-form__select-labels">
            <div class="unsubscribe-form__select-label">Subscribed</div>
            <div class="unsubscribe-form__select-label">Unsubscribed</div>
          </div>
          <div
            v-for="(label, i) in labelsForCheckboxes"
            :key="i"
            class="d-flex unsubscribe-form__select-row"
          >
            <Checkbox marginRight="85px" marginLeft="36px" />
            <Checkbox marginRight="70px" />
            <span class="unsubscribe-form__select-row-label">{{ label }}</span>
            <div v-if="isShowMobileCheckboxes(i)" class="d-flex ml-2 mb-5">
              <Checkbox label="Android" id="android" />
              <Checkbox label="IOS" class="ml-2" id="ios" />
            </div>
          </div>
          <span class="unsubscribe-form__select-btn unsubscribe-form__select-btn--cancel">Cancel</span>
          <span class="unsubscribe-form__select-btn unsubscribe-form__select-btn--submit">Submit</span>
        </div>
      </div>

      <div class="unsubscribe-form__current">
        <h3 class="unsubscribe-form__current-title">Your current account settings</h3>
        <div class="unsubscribe-form__current-question">
          <h4>Levels you are interested in</h4>
          <div class="unsubscribe-form__current-question-radios">
            <RadioButton
              v-for="(btn, i) in labelsForRadioButtonLevels"
              :key="i"
              :label="btn"
              name="labelsForRadioButtonLevels"
              class="mr-2 mb-1"
            />
          </div>
        </div>
        <div class="unsubscribe-form__current-question">
          <h4>Characters</h4>
          <div class="unsubscribe-form__current-question-radios">
            <RadioButton
              v-for="(btn, i) in labelsForCharacters"
              :key="i"
              :label="btn"
              name="labelsForCharacters"
              class="mr-2 mb-1"
            />
          </div>
        </div>
      </div>
    </section>
    <Footer />
  </div>
</template>

<script>
import Header from "./components/Header";
import Checkbox from "./components/Checkbox";
import RadioButton from "./components/RadioButton";
import Footer from "./components/Footer";

export default {
  name: "App",
  components: {
    Header,
    Checkbox,
    RadioButton,
    Footer
  },
  data: () => ({
    labelsForCheckboxes: [
      "Marketing",
      "Weekly New Lessons",
      "Word of the Day",
      "New Apps"
    ],
    labelsForRadioButtonLevels: ["newbie", "intermediate", "advanced"],
    labelsForCharacters: [
      "simplified",
      "traditional",
      "not interested learning characters"
    ]
  }),
  methods: {
    isShowMobileCheckboxes(index) {
      return index === this.labelsForCheckboxes.length - 1;
    }
  }
};
</script>

<style lang="scss">
@import "./style/global.scss";
$grey: #f2f2f2;
$dark-grey: #979898;
$blue: #509fe4;

.unsubscribe {
  &-info {
    flex-direction: column;
    align-items: center;
    background-image: url("./assets/bg2.png");
    background-repeat: no-repeat;
    background-position: bottom center;
    background-size: cover;

    &__title {
      color: #fff;
      font-weight: 400;
      font-size: 32px;
    }

    &__content {
      justify-content: space-between;
      width: 60%;
      padding-bottom: 150px;
    }

    &__video {
      flex: 1;
      margin-right: 36px;
      border: 6px solid #fff;
      border-radius: 4px;
    }

    &__feedback {
      flex: 1;
      max-width: calc(50% - 36px);

      &-title {
        font-size: 18px;
        font-weight: 400;
        color: #fff;
      }

      textarea {
        width: 100%;
        height: 200px;
        resize: none;
        padding: 8px;
        box-sizing: border-box;

        &:focus {
          outline-color: #e44c4c;
        }
      }
    }
  }

  &-form {
    justify-content: center;
    margin-bottom: 100px;
    padding-top: 50px;

    &__select-label {
      font-weight: 700;
      margin-bottom: 16px;

      &:first-child {
        margin-right: 16px;
      }
    }

    &__select-btn {
      padding: 8px 40px;
      border-radius: 4px;
      cursor: pointer;
      transition: 0.3s;

      &--cancel {
        background-color: $grey;
        color: $dark-grey;
        margin-right: 16px;

        &:hover {
          background-color: $dark-grey;
          color: #fff;
        }
      }

      &--submit {
        background-color: $blue;
        text-transform: uppercase;
        color: #fff;

        &:hover {
          background-color: #fff;
          color: $blue;
          border: 1px solid $blue;
        }
      }
    }

    &__current {
      background-color: #f6fafd;
      border: 3px solid $blue;
      border-radius: 20px;
      margin-left: 120px;

      &-question {
        width: calc(80% - 40px);
        padding: 0 20px;
        box-sizing: border-box;

        &-radios {
          display: flex;
          flex-wrap: wrap;
        }
      }

      &-title {
        padding: 10px;
        background-color: #e8f3f9;
        margin: 0;
        border-top-left-radius: 20px;
        border-top-right-radius: 20px;
        color: $blue;
        margin: 0;
        text-align: center;
        font-size: 20px;
      }
    }
  }
}
</style>
