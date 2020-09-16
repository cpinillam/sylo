<template>
    <div class="mainBody">
        <today-data :period="period"></today-data>
        <five-days-data :period="period"></five-days-data>
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
            period: String
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