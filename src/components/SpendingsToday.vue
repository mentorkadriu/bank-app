<template>
  <h4>Today <vue-feather type="chevron-down" size="16"></vue-feather></h4>
  <BaLine/>
  <ul>
    <SpendingItem
      v-for="spending in spendings"
      :title="spending.title"
      :amount="spending.amount"
      :key="spending.id"
    />
  </ul>
</template>

<script>
import SpendingItem from "@/components/SpendingItem";
import BaLine from "@/components/BaLine";
export default {
  name: "SpendingsToday",
  components: {BaLine, SpendingItem },
  props: {
    spendings: {
      type: Array,
      required: true,
    },
  },
};
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
</style>
