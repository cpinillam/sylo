<template>
    <div class="fiveDaysData" v-if="isselectedPeriod">


        <div class="mainData">
            <div class="MainHeader__nav-bottom">
                <btn-primary title="Stock"></btn-primary>
                <btn-primary title="Consumption average"></btn-primary>
            </div>

            <main-chart></main-chart>

        </div>

    </div>
</template>

<script>


    import MainChart from "../chart/mainChart";
    import BtnPrimary from "../../botons/btnPrimary";
    export default {
        name: "fiveDaysData",
        components: {
            BtnPrimary,
            MainChart
        },
        props:{
            period: String
        },

        computed:{
            isselectedPeriod(){
                return this.period === "LAST 5 DAYS"
            }
        }
    }
</script>

<style lang="scss">
    @import "../../../assets/scss/variables_colors";
    .fiveDaysData {
        width: 100%;
        display: flex;
        align-items: center;
        flex-direction: column;
    }
    .mainData {
        width: 100%;
        background-color: white;
        border-radius: 40px;
        padding: 20px;
        position: relative;
        display: flex;
        justify-content: center;
        flex-direction: column;





    }

</style>