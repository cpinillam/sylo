<template>
  <div id="app">
    <main-header @selectButtonPeriod="selectPeriod"></main-header>
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
          stockData: {}
      }
    },

      created() {
        this.getData();


      },
      methods:{

        selectPeriod(currentPeriod) {
            this.period = currentPeriod
          },


        async getData(){
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

