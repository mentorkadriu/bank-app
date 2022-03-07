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
                  <ion-button fill="clear"  router-link="/tabs/tab1" router-direction="forward">
                    Start Now  <vue-feather type="arrow-right"></vue-feather>
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
import { defineComponent } from 'vue';
import {IonPage, IonContent, IonGrid, IonRow, IonCol, IonButton} from '@ionic/vue';

export default defineComponent({
  name: 'OnboardingPage',
  components: { IonContent, IonPage, IonGrid, IonRow, IonCol, IonButton },
});
</script>
<style scoped>
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
.onboarding a i {
  vertical-align: middle;
}
ion-grid, ion-row {
  height: 100%;
}
.onboarding {
  padding: 36px;
}
.onboarding__title {
  font-family: Frank Ruhl Libre;
  font-style: normal;
  font-weight: 900;
  font-size: 58px;
  line-height: 72px;
  color: #fff;
  margin-bottom: 40px;
}
.onboarding__nav {
  display: flex;
  width: 100%;
  justify-content: space-between;
  align-items: center;
}
.onboarding__nav__bullets {
  margin: 0;
  padding: 0;
  list-style: none;
}
.onboarding__nav__bullets li {
  height: 12px;
  width: 12px;
  margin-right: 12px;
  border-radius: 50%;
  background-color: #fff;
  opacity: 0.3;
  display: inline-block;
}
.onboarding__nav__bullets li.active {
  background-color: #f26014;
  opacity: 1;
}
.onboarding__nav__bullets li a {
  display: none;
}

</style>
