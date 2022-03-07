<template>
  <nav class="navigation">
    <router-link to="/dashboard">
      <vue-feather type="credit-card" size="24"></vue-feather>
    </router-link>
    <router-link to="/">
      <vue-feather type="bell"></vue-feather>
    </router-link>
    <router-link to="/spendings">
      <vue-feather type="message-square"></vue-feather>
    </router-link>
  </nav>
</template>

<script>
export default {
  name: "BaNavigation",
};
</script>

<style scoped lang="scss">
.navigation {
  position: absolute;
  bottom: 0;
  left: 0;
  width: 100%;
  display: flex;
  justify-content: space-evenly;
  align-items: center;
  background: #ffffff;
  box-shadow: 0px -4px 24px rgba(0, 24, 71, 0.08);
  padding-top: 26px;
  padding-bottom: 38px;
  z-index: 100;
  a {
    color: #25265e;
    text-decoration: none;
    i.vue-feather {
      font-size: 24px;
      color: #25265e;
      opacity: 0.4;
    }
    &.router-link-active {
      i.vue-feather {
        color: #25265e;
        opacity: 1;
      }
    }
  }
}
</style>
