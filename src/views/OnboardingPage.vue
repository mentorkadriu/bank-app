<template>
  <ion-page>
    <ion-content :fullscreen="true">
      <ion-grid>
        <ion-row class="ion-align-items-end">
          <ion-col>
            <div class="onboarding">
              <div class="onboarding__inner">
                <h2 class="onboarding__title">Smart Savings</h2>
                <div class="onboarding__nav">
                  <ul class="onboarding__nav__bullets">
                    <li class="active"><a href="#">1</a></li>
                    <li><a href="#">2</a></li>
                    <li><a href="#">3</a></li>
                  </ul>
                  <ion-button fill="clear" router-link="/tabs/tab1" router-direction="forward">
                    Start Now
                    <vue-feather type="arrow-right"></vue-feather>
                  </ion-button>
                </div>
              </div>
            </div>
          </ion-col>
        </ion-row>
      </ion-grid>
    </ion-content>
  </ion-page>
</template>

<script lang="ts">
import {defineComponent} from 'vue';
import {IonPage, IonContent, IonGrid, IonRow, IonCol, IonButton} from '@ionic/vue';

export default defineComponent({
  name: 'OnboardingPage',
  components: {IonContent, IonPage, IonGrid, IonRow, IonCol, IonButton},
});
</script>
<style scoped lang="scss">
ion-content {
  --background: center / cover no-repeat url("../../resources/images/Bank-app__onboarding@2x.png") fixed;
}

ion-button {
  --color: #fff;
  text-transform: none;
  font-family: "Circular Std", "sans-serif";
  font-style: normal;
  font-weight: bold;
  font-size: 18px;
  line-height: 27px;
  text-decoration: none;
}

ion-grid, ion-row {
  height: 100%;
}

a i {
  vertical-align: middle;
}

.onboarding {
  padding: 36px;

  &__title {
    font-family: Frank Ruhl Libre;
    font-style: normal;
    font-weight: 900;
    font-size: 58px;
    line-height: 72px;
    color: #ffffff;
    margin-bottom: 40px;
  }

  &__nav {
    display: flex;
    width: 100%;
    justify-content: space-between;
    align-items: center;

    &__bullets {
      margin: 0;
      padding: 0;
      list-style: none;

      li {
        height: 12px;
        width: 12px;
        margin-right: 12px;
        border-radius: 50%;
        background-color: #ffffff;
        opacity: 0.3;
        display: inline-block;

        &.active {
          background-color: $color-flamingo;
          opacity: 1;
        }

        a {
          display: none;
        }
      }
    }
  }

  a {
    font-family: $font-circular;
    font-style: normal;
    font-weight: bold;
    font-size: 18px;
    line-height: 27px;
    color: #ffffff;
    text-decoration: none;

    i {
      vertical-align: middle;
    }
  }
}


</style>
