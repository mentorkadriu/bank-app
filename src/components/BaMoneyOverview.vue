<template>
  <div>
    <ion-img :src="imgSrc" :alt="title" />
    <h5>{{ title }}</h5>
    <p>{{ amount }}</p>
  </div>
</template>

<script>
import {IonImg} from "@ionic/vue";

export default {
  name: "BaMoneyOverview",
  props: {
    amount: {
      type: String,
      default: "$0.00",
    },
    title: {
      type: String,
      default: "",
    },
    imgSrc: {
      type: String,
      default: "",
    },
  },
  components: {IonImg}
};
</script>

<style scoped>
ion-img {
  max-width: 56px;
  height: auto;
}
h5 {
  font-style: normal;
  font-weight: 500;
  font-size: 14px;
  line-height: 20px;
  color: rgba(37, 38, 94, 0.4);
}
p {
  font-style: normal;
  font-weight: 900;
  font-size: 24px;
  line-height: 36px;
  color: #25265e;
}
</style>
