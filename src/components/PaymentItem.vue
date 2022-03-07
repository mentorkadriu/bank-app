<template>
  <li>
    <div class="logo__wrapper">
        <div class="logo" :style="{backgroundColor: color}">
          <vue-feather :type="icon" size="24" />
        </div>
        <div class="name__wrapper">
          <span class="name">{{ name }}</span>
          <br>
          <span class="date">Next payment: {{ date }}</span>
        </div>
    </div>
    <div>
      <span class="amount">{{ amount }}/mth</span>
    </div>
  </li>
  <li>
    <BaLine :style="{width: '100%'}"/>
  </li>
</template>

<script>
import {computed} from "vue";
import BaLine from "@/components/BaLine";

export default {
  name: "PaymentItem",
  components: {BaLine},
  props: {
    name: String,
    amount: String,
    color: {
      type: String,
      default: "#d3d3d3"
    },
    date: String,
  },
  setup(props) {
    const icon = computed(() => props.name.toLowerCase() || "feather");
    return {
      icon
    };
  },
};
</script>

<style scoped>
.logo {
  width: 64px;
  height: 58px;
  display: flex;
  justify-content: center;
  align-items: center;
  box-shadow: 0px 4px 24px rgba(0, 24, 71, 0.18);
  border-radius: 8px;
}
.logo__wrapper {
  display: flex;
}
.logo i {
  color: #fff;
}
li {
  display: flex;
  justify-content: space-between;
  align-items: center;
  margin-bottom: 16px;
}
.name {
  font-style: normal;
  font-weight: 500;
  font-size: 18px;
  line-height: 28px;
  color: #25265E;
}
.name__wrapper {
  margin-left: 16px;
}
.date {
  font-style: normal;
  font-weight: 450;
  font-size: 12px;
  line-height: 24px;
  color: rgba(37, 38, 94, 0.4);
}
.amount {
  font-weight: bold;
  font-size: 18px;
  line-height: 24px;
  text-align: right;
  color: rgba(37, 38, 94, 0.7);
}
</style>
