<template>
    <div class="mainBody">
        <today-data :period="period" :main-data="mainData"></today-data>
        <five-days-data :period="period" :main-data="mainData"></five-days-data>
    </div>
</template>

<script>
    import TodayData from "./bodyData/todayData";
    import FiveDaysData from "./bodyData/fiveDaysData";
    export default {
        name: "mainBody",
        components: {TodayData, FiveDaysData},
        data (){
            return {
                today: false,
                fiveDays: true
            }
        },
        props: {
            period: String,
            mainData: Object

        }


    }
</script>

<style lang="scss" scoped>

    .mainBody {
        padding: 20px;
        margin-bottom: 100px;
        width: 100%;
    }
</style>