<template>
  <li>
    <span>{{ title }}</span>
    <span>{{ amount }}</span>
  </li>
</template>

<script>
export default {
  name: "SpendingItem",
  props: {
    title: String,
    amount: String,
  },
};
</script>

<style scoped>
li {
  display: flex;
  justify-content: space-between;
  align-items: center;
  margin-bottom: 16px;
}
li span {
  font-style: normal;
  font-weight: 500;
  font-size: 16px;
  line-height: 24px;
  color: #25265e;
}
li span:last-child {
  color: #f26014;
}
</style>
