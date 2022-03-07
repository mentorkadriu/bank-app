<template>
  <h4>Scheduled payments <vue-feather type="chevron-right" size="16" class="right"></vue-feather></h4>
  <BaLine/>
  <ul>
    <PaymentItem
      v-for="payment in payments"
      :name="payment.name"
      :amount="payment.amount"
      :date="payment.date"
      :color="payment.color"
      :key="payment.id"
    />
  </ul>
</template>

<script>
import {defineComponent} from "vue";
import BaLine from "@/components/BaLine";
import PaymentItem from "@/components/PaymentItem";

export default defineComponent({
  name: "ScheduledPayments",
  components: {PaymentItem, BaLine },
  props: {
    payments: {
      type: Array,
      required: true,
    },
  },
});
</script>

<style scoped>
h4 {
  font-weight: 500;
  font-size: 18px;
  line-height: 27px;
  color: #32027e;
  margin-bottom: 8px;
  vertical-align: middle;
}
h4 i {
  vertical-align: middle;
}
.ba-line {
  margin-bottom: 20px;
}
ul {
  list-style: none;
  padding: 0;
}
.right {
  float: right;
}
</style>
