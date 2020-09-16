<template>
  <div id="app">
    <main-header @selectinga="selectButtoni"></main-header>
    <main-body :period="period" ></main-body>
    <main-footer></main-footer>
   </div>
</template>

<script>
  import MainHeader from "./components/layout/mainHeader";
  import MainFooter from "./components/layout/mainFooter";
  import MainBody from "./components/layout/mainBody";

  export default {
    components: {MainBody, MainFooter, MainHeader},
    data (){
      return {
        period: 'TODAY'
      }
    },
    methods:{
      selectButtoni(buttonistas) {
        this.period = buttonistas
      },
    }
  }

</script>
<style lang="scss">
    @import "assets/scss/variables_colors";

</style>
