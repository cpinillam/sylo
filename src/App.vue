<template>
  <div id="app">
    <main-header @selectinga="selectButtoni"></main-header>
    <main-body :period="period" :main-data="stockData" ></main-body>
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
        period: 'TODAY',
          info: {},
          stockData: {}
      }
    },

      created() {
        this.getEntradas();


      },
      methods:{

        selectButtoni(buttonistas) {
            this.period = buttonistas
          },

        setData (response){
            this.stockData.current_stock = response.data.current_stock;

        },

        async getEntradas(){
            const axios = require('axios');
            {
                axios.get('data/data.json')
                    .then(response => {
                        this.stockData = response.data;


                    })
                    .catch(error => console.log(error))
            }
        }
    }


  }

</script>
<style lang="scss">
    @import "assets/scss/variables_colors";

</style>
