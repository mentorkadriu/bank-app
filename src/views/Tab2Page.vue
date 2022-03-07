<template>
  <ion-page>
    <ion-content :fullscreen="true">
      <div class="nav__wrapper">
        <ion-button fill="clear"  router-link="/tabs/tab1" router-direction="back">
          <vue-feather type="chevron-left" size="24px" color="primary"></vue-feather>
        </ion-button>
      </div>
      <div class="content-padding">
        <div class="spendings">
          <h3 class="spendings__amount">
            Spendings
          </h3>
          <div class="spendings__amount__container">
            <div class="spendings__amount__value">
            <span>
            $2,400.00
            </span>
            </div>
            <div class="spendings__amount__period">
              <span> 12%</span>
              <p>vs past month</p>
            </div>
          </div>
        </div>
        <div class="chart-selector">
          <div class="chart-selector__item active">
          <span>
            Day
          </span>
          </div>
          <div class="chart-selector__item">
          <span>
            Week
          </span>
          </div>
          <div class="chart-selector__item">
          <span>
            Month
          </span>
          </div>
          <div class="chart-selector__item">
          <span>
            Custom
          </span>
          </div>
        </div>
      </div>
      <div class="chart-container">
        <ion-img src="./assets/images/chart.svg"></ion-img>
      </div>
      <div class="content-padding">
        <ScheduledPayments :payments="payments"></ScheduledPayments>
      </div>
    </ion-content>
  </ion-page>
</template>

<script lang="ts">
import { defineComponent } from 'vue';
import {IonPage, IonContent, IonImg, IonButton} from '@ionic/vue';
import ScheduledPayments from '../components/ScheduledPayments.vue';

export default defineComponent({
  name: 'Tab2Page',
  components: { IonContent, IonPage, IonImg, ScheduledPayments, IonButton },
  setup(){
    const payments = [{
      id: 1,
      name: 'Youtube',
      amount: '$3.99',
      date: '12/04',
      color: '#FE5145',
    }, {
      id: 2,
      name: 'Github',
      amount: '$3.99',
      date: '12/04',
      color: '#13151B',
    }, {
      id: 3,
      name: 'Radio',
      amount: '$3.99',
      date: '12/04',
      color: 'rgb(69 169 254)',
    }, {
      id: 4,
      name: 'Upload-Cloud',
      amount: '$3.99',
      date: '12/04',
      color: 'rgb(181 181 181)',
    }];
    return {
      payments
    }
  }
});
</script>
<style>
.content-padding {
  padding: 0 32px;
}
.nav__wrapper {
  padding-top: 40px;
  padding-bottom: 26px;
  padding-left: 8px;
}
.chart-selector {
  display: flex;
  justify-content: space-around;
  margin: 32px 0;
}
.chart-selector__item {
  font-size: 16px;
  line-height: 24px;
  color: rgba(37, 38, 94, 0.4);
  padding: 6px 0;
  border-radius: 24px;
  display: flex;
  justify-content: center;
  flex-grow: 1;
}
.chart-selector__item.active {
  font-weight: bold;
  color: #FFF;
  background: #5D0CE1;
}
.spendings__amount {
  font-weight: bold;
  font-size: 18px;
  line-height: 27px;
  color: rgba(37, 38, 94, 0.7);
}
.spendings__amount__container {
  display: flex;
}
.spendings__amount__value {
  font-weight: 900;
  font-size: 36px;
  line-height: 40px;
  color: #25265E;
  margin-right: 16px;
}
.spendings__amount__period span{
  font-size: 16px;
  line-height: 24px;
  color: #1CD5CF;
}
.spendings__amount__period span:first-child::before {
  content: "";
  width: 0;
  height: 0;
  border-style: solid;
  border-width: 10px 5px 0 5px;
  border-color: #1CD5CF transparent transparent transparent;
  display: inline-flex;
}
.spendings__amount__period p {
  font-weight: 500;
  font-size: 14px;
  line-height: 20px;
  color: rgba(37, 38, 94, 0.4);
  margin: 0;
  padding: 0;
}
</style>
