<template>
  <div id="app">
    <div id="nav">
      <router-link to="/">Home</router-link> |
      <router-link to="/about">About</router-link>
    </div>

    <btn-primary></btn-primary>
    <btn-back></btn-back>
    <btn-config></btn-config>
    <btn-days-stock></btn-days-stock>

    <router-view/>
  </div>
</template>

<script>
  import BtnPrimary from "./components/botons/btnPrimary";
  import BtnBack from "./components/botons/btnBack";
  import BtnConfig from "./components/botons/btnConfig";
  import BtnDaysStock from "./components/botons/btnDaysStock";

  export default {
    components: {BtnDaysStock, BtnConfig, BtnBack, BtnPrimary}
  }

</script>
<style lang="scss">
    @import "assets/scss/variables_colors";

</style>
