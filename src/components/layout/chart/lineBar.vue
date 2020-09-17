<template>
    <svg height="200" width="100%" viewBox="0 0 265 230" >
        <path  class="cls-1 ts2" d="M35.91,173.66a108.2,108.2,0,0,1,91.65-155,108.23,108.23,0,0,1,102.84,60,109.8,109.8,0,0,1,10.44,61.16,108.69,108.69,0,0,1-9.91,33.86"/>
        <path :style="'stroke-dashoffset:' + getValueToGraph(stock)" class="cls-1" d="M35.91,173.66a108.2,108.2,0,0,1,91.65-155,108.23,108.23,0,0,1,102.84,60,109.8,109.8,0,0,1,10.44,61.16,108.69,108.69,0,0,1-9.91,33.86"/>

    </svg>
</template>

<script>
    export default {
        name: "lineBar",
        props:{
            stock: Number,
            maxCapacity: Number
        },

        created() {
            this.total = "--stroke-dashoffset:" + this.valueTotal
        },
        methods: {
            convertToGraph(stockPercent){
                let maxTons = 100;
                let minTons = 0;
                let maxPathValue = 460;
                let minPathValue = 15;
                let refvalue = (maxPathValue-minPathValue)/(maxTons-minTons);
                return maxPathValue-(stockPercent*refvalue);

            },

            getPercentStock(stockKilos){
                let refValue = this.maxCapacity/100;
                return stockKilos/refValue;
            },

            getValueToGraph(stockKilos){
                let percentStock = this.getPercentStock(stockKilos);
                return this.convertToGraph(percentStock);

            },

            kiloToTons(bigFloat){
                return (bigFloat/1000).toString().slice(0, 5);
            },



        }


    }
</script>

<style lang="scss" scoped>

    .cls-1{
        fill:none;stroke:#4697aa;stroke-miterlimit:10;stroke-width:20px;
        stroke-dasharray: 450;
        stroke-linecap: round;
    }

    .ts2 {
        stroke: #d9dae5 !important;
    }

    .st9{
        fill:#2D2E83;
        font-family:'Montserrat'; font-weight: 700;
        font-size:14px;}

</style>