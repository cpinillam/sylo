<template>
    <div class="todayData animaSlideIn" v-if="isselectedPeriod">
        <div class="mainMeasure">
            <p class="animaTransition" :class="{paragraphGraph : !graph }">
                {{currentDate()}}<br>
                <span>{{kiloToTons(mainData.maxCapacity)}} Tons of Max Capacity
                </span>
            </p>

            <central-data class="clickable" @mainview="selectView" :graph="graph" :status="mainData.status" :stock="mainData.current_stock" :max-capacity="mainData.maxCapacity">
            </central-data>

            <div class="currentWeight animaTransition" :class="{graphline : graph }">
                <i class="fas fa-weight-hanging">
                </i>
               {{kiloToTons(mainData.current_stock)}}
                <span>Tons</span>
            </div>
        </div>
        <div class="todayConsumption">
           <div class="title"> Consumption Average</div>
            <div class="text">
                <i class="fas fa-weight-hanging">
                </i> {{kiloToTons( mainData.average_consumption)}}
                <span>Tons per day</span>
            </div>
        </div>
        <BtnDaysStock :eta="mainData.eta" :status="mainData.status" >
        </BtnDaysStock>
    </div>
</template>

<script>

    import BtnDaysStock from "../../../components/botons/btnDaysStock";
    import CentralData from "./centralData";
    export default {
        name: "todayData",
        components: {
            CentralData,
            BtnDaysStock
        },

        data(){
            return {
                graph:false,
                currentDay:"30/08/1989"
            }
        },
        props:{
            period:String,
            mainData: Object
        },

        computed:{
            isselectedPeriod(){
                return this.period === "TODAY"
            }

        },
        methods: {

            kiloToTons(bigFloat) {
                return (bigFloat / 1000).toString().slice(0, 5);
            },

            currentDate(){
               this.currentDay = this.mainData.last_update;
                if (!this.currentDay) return 1;
               return (this.currentDay).toString().slice(0, 10);
            },

            selectView(view){
                    this.graph = view === 'viewGraph';
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
        align-items: center;
        flex-direction: column;

        p{
            font-family: 'Montserrat', sans-serif;
            font-weight: 700;
            color: $main-low;
            font-size: 1.5rem;
            text-align: center;
            line-height: 20px;

            span {
                font-size: 0.8rem;
            }

        }

        .paragraphGraph {
            font-size: 1rem;
            position: absolute;
            left: 20px;
            top: 50%;
            transform: translateY(-50%);
            text-align: left;

            span {
               visibility: hidden;
            }
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

        .graphline {

            right: 50%;
            bottom: 5%;
            transform: translatex(50%);

        }
    }

    .todayConsumption {
        width: 100%;
        margin-top: 40px;
        margin-bottom: 30px;
        display: flex;
        flex-direction: column;
        align-items: center;
        font-size: 1.0em;
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
    .clickable {
        cursor: pointer
    }

</style>