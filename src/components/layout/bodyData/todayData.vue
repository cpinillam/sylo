<template>
    <div class="todayData" v-if="isselectedPeriod">
        <div class="mainMeasure">
            <sylo-svg class="syloSvg"></sylo-svg>
            <div class="currentWeight">
                <i class="fas fa-weight-hanging"></i>
                17.5
                <span> Tons</span>
            </div>
        </div>
        <div class="todayConsumption">
           <div class="title"> Consumption</div>
            <div class="text"> <i class="fas fa-weight-hanging"></i> 3.02 <span>Tons per day</span></div>
        </div>
        <BtnDaysStock></BtnDaysStock>
    </div>
</template>

<script>

    import BtnDaysStock from "../../../components/botons/btnDaysStock";
    import SyloSvg from "../../svg/syloSvg";
    export default {
        name: "todayData",
        components: {
            SyloSvg,
            BtnDaysStock
        },
        props:{
            period:String

        },
        computed:{
            isselectedPeriod(){
                return this.period === "TODAY"
            }
        }

    }
</script>

<style lang="scss" scoped>
    @import "../../../assets/scss/variables_colors";
    .todayData {
        width: 100%;
        display: flex;
        align-items: center;
        flex-direction: column;
    }
    .mainMeasure {
        width: 100%;
        background-color: white;
        border-radius: 40px;
        padding: 20px;
        position: relative;
        display: flex;
        justify-content: center;


        .syloSvg {
            width: 130px;
            margin-top: -40px;
            margin-bottom: -40px;
        }

        .currentWeight {
            position: absolute;
            right: 5%;
            top: 50%;
            display: flex;
            flex-direction: column;
            align-items: center;
            border-radius: 50px;
            border: solid 1px $main-high;
            transform: translateY(-50%);
            padding: 20px 10px 20px 10px;
            font-size: 1.5rem;
            font-family: 'Montserrat';
            font-weight: 700;
            color: $main-low;

            i {
                font-size: 1.2rem;
                margin-bottom: 10px;
            }

            span {
                font-size: .9rem;
                font-weight: 200;
                color: $main-high;
            }

        }
    }

    .todayConsumption {
        width: 100%;
        margin-top: 40px;
        margin-bottom: 30px;
        display: flex;
        flex-direction: column;
        align-items: center;
        font-size: 1.1rem;
        font-family: 'Montserrat', sans-serif;
        color: $main-low;

        .title {
            font-weight: 500;
            margin-bottom: 10px;
        }

        .text {
            font-weight: 700;

            i {
                font-size: 1.5rem;
                margin-right: 20px;
            }

            span {
                font-size: 1rem;
                color: $main-mid;
                font-weight: 400;
            }
        }
    }

</style>