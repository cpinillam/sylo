<template>
    <div class="fiveDaysData animaSlideIn" v-if="isSelectedPeriod">
        <div class="mainData">
            <div class="MainHeader__nav-bottom">
                <btn-primary style="pointer-events: none;" title="Stock" >
                </btn-primary>
                <btn-primary style="pointer-events: none;" title="Consumption average">
                </btn-primary>
            </div>
            <main-chart :timeseries="mainData.timeseries">
            </main-chart>
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
            period: String,
            mainData: Object
        },

        computed:{
            isSelectedPeriod(){
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