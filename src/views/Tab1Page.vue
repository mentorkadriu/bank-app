<template>
  <ion-page>
    <ion-content :fullscreen="true">

      <div class="dashboard">
        <div class="dashboard__top">
          <div class="nav">
            <ion-button fill="clear"  router-link="/" router-direction="back">
              <vue-feather type="home"></vue-feather>
            </ion-button>
          </div>
        </div>
        <div class="dashboard__bottom">
          <div class="dashboard__bottom__profile">
            <div class="profile">
              <div class="profile__info">
                <div class="profile__avatar">
                  <ion-img src="./assets/images/avatar/user.png" alt="John Doe" />
                </div>
                <div class="profile__user">
                  <h4>John Doe</h4>
                  <a href="mailto:@johndoe">@johndoe</a>
                </div>
              </div>
              <BaLine/>
              <div class="profile__balance">
                <div class="profile__balance__logo">
                  <p>Available balance</p>
                  <ion-img src="./assets/images/visalogo@2x.png" alt="visa logo" />
                </div>
                <div class="profile__amount">$12,496.00</div>
                <div class="profile__card">
                  <span>****</span>
                  <span>****</span>
                  <span>****</span>
                  <span>2077</span>
                </div>
              </div>
            </div>
          </div>
          <div class="money-transfers">
            <div class="money-transfers__item">
              <BaMoneyOverview img-src="./assets/images/bag.svg" title="Cashback" amount="$220.54" />
            </div>
            <div class="money-transfers__item right">
              <BaMoneyOverview
                  img-src="./assets/images/safe.svg"
                  title="Safe Deposit"
                  amount="$12,800.64"
              />
            </div>
          </div>
          <SpendingsToday :spendings="spendings" />
        </div>
        <!-- ./dashboard__bottom -->
      </div>
    </ion-content>
  </ion-page>
</template>

<script lang="ts">
import { defineComponent } from 'vue';
import {IonPage, IonContent, IonImg, IonButton} from '@ionic/vue';
import BaMoneyOverview from '../components/BaMoneyOverview.vue';
import SpendingsToday from '../components/SpendingsToday.vue';
import BaLine from "@/components/BaLine.vue";

export default  defineComponent({
  name: 'Tab1Page',
  components: {BaLine, IonContent, IonPage, BaMoneyOverview, SpendingsToday, IonImg, IonButton },
  setup() {
    const spendings = [
      {
        title: "Steam Store",
        amount: "-$19.99",
        id: 1,
      },
      {
        title: "Amazon",
        amount: "-$30.00",
        id: 2,
      },
      {
        title: "Netflix",
        amount: "-$9.00",
        id: 2,
      },
    ];
    return {
      spendings,
    };
  },
});
</script>
<style scoped>
.dashboard {
  display: flex;
  flex-direction: column;
  width: 100%;
  background: url("../../resources/images/Bank-app__dashboard@2x.png") no-repeat center center;
  background-size: cover;
  min-height: 100%;
}
.dashboard__top {
  height: 276px;
}
.dashboard__bottom {
  flex-grow: 0.66;
  background-color: #fff;
  padding-left: 24px;
  padding-right: 24px;
}
.dashboard__bottom__profile {
  position: relative;
  padding-bottom: 50%;
  height: 0;
  width: 100%;
}
.nav {
  height: 48px;
  width: 48px;
  border-radius: 50%;
  background-color: #fff;
  display: flex;
  justify-content: center;
  align-items: center;
  margin-top: 24px;
  margin-left: 28px;
}
.profile {
  background: #fff;
  box-shadow: 0px -8px 24px rgba(0, 24, 71, 0.12);
  border-radius: 12px;
  width: 100%;
  padding-left: 20px;
  padding-right: 20px;
  padding-bottom: 20px;
  position: relative;
  left: 50%;
  top: 50%;
  transform: translate(-50%, -50%);
  z-index: 1;
}
.profile__info {
  display: flex;
  margin-bottom: 16px;
}
.profile__avatar {
  background: #fff;
  box-shadow: 0px -4px 12px rgba(0, 24, 71, 0.12);
  width: 73px;
  overflow: hidden;
  margin-top: -20px;
  border-radius: 5px;
}
.profile__avatar ion-img {
  max-width: 100%;
  height: auto;
  display: block;
}
.profile__card {
  display: flex;
  justify-content: space-between;
  align-items: center;
  margin-top: 16px;
}
.profile__card span {
  font-style: normal;
  font-weight: bold;
  font-size: 24px;
  line-height: 33px;
  color: rgba(37, 38, 94, 0.7);
}
.profile__balance {
  margin-top: 16px;
}
.profile__balance__logo {
  display: flex;
  justify-content: space-between;
  align-items: center;
}
.profile__balance__logo p {
  font-style: normal;
  font-weight: 500;
  font-size: 14px;
  line-height: 20px;
  color: rgba(37, 38, 94, 0.4);
}
.profile__balance__logo ion-img {
  max-width: 52px;
}
.profile__amount {
  font-style: normal;
  font-weight: 900;
  font-size: 32px;
  line-height: 40px;
  color: #25265e;
  margin-bottom: 45px;
}
.profile__user {
  display: flex;
  flex-direction: column;
  justify-content: center;
  margin-left: 16px;
}
.profile__user h4 {
  font-style: normal;
  font-weight: bold;
  font-size: 18px;
  line-height: 27px;
  color: #25265e;
}
.profile__user a {
  font-style: normal;
  font-weight: 500;
  font-size: 14px;
  line-height: 20px;
  color: rgba(37, 38, 94, 0.4);
  text-decoration: none;
}
.money-transfers {
  display: flex;
  justify-content: space-between;
  margin-bottom: 48px;
}
.money-transfers__item {
  display: flex;
  flex-direction: column;
  width: 50%;
}

.money-transfers__item.right {
  align-items: end;
}

.money-transfers > div:first-child{
  border-right: 1px solid #e6e6e6;
}

</style>
