<template>
    <svg height="500" width="100%" viewBox="0 0 317.7 400" >

        <g id="dia1" class="clickable animaScale" @click="selectDay(0)">
	        <line class="st0" x1="58.8" y1="354.2" x2="58.8" y2="138.3" :style="'stroke-dashoffset:' + convertTograph(kiloToTons(timeseries.stock[0]))"/>
            <line class="st1" x1="74.8" y1="354.2" x2="74.8" y2="138.3" :style="'stroke-dashoffset:' + convertTograph(kiloToTons(timeseries.avg_dcr[0]))"/>
</g>
        <g id="dia2" class="clickable animaScale" @click="selectDay(1)">
	        <line class="st0" x1="110" y1="354.2" x2="110" y2="138.3" :style="'stroke-dashoffset:' + convertTograph(kiloToTons(timeseries.stock[1]))"/>
            <line class="st1" x1="126" y1="354.2" x2="126" y2="138.3" :style="'stroke-dashoffset:' + convertTograph(kiloToTons(timeseries.avg_dcr[1]))"/>
</g>
        <g id="dia3" class="clickable animaScale" @click="selectDay(2)">
	        <line class="st0" x1="161.5" y1="354.2" x2="161.5" y2="138.3" :style="'stroke-dashoffset:' + convertTograph(kiloToTons(timeseries.stock[2]))"/>
            <line class="st1" x1="177.5" y1="354.2" x2="177.5" y2="138.3" :style="'stroke-dashoffset:' + convertTograph(kiloToTons(timeseries.avg_dcr[2]))"/>
</g>
        <g id="dia4" class="clickable animaScale" @click="selectDay(3)">
	        <line class="st0" x1="213" y1="354.2" x2="213" y2="138.3" :style="'stroke-dashoffset:' + convertTograph(kiloToTons(timeseries.stock[3]))"/>
            <line class="st1" x1="229" y1="354.2" x2="229" y2="138.3" :style="'stroke-dashoffset:' + convertTograph(kiloToTons(timeseries.avg_dcr[3]))"/>
</g>
        <g id="dia5" class="clickable animaScale" @click="selectDay(4)">
	        <line id="st0" class="st0" x1="268" y1="354.2" x2="268" y2="138.3" :style="'stroke-dashoffset:' + convertTograph(kiloToTons(timeseries.stock[4]))"/>
            <line id="st1" class="st1" x1="284" y1="354.2" x2="284" y2="138.3" :style="'stroke-dashoffset:' + convertTograph(kiloToTons(timeseries.avg_dcr[4]))"/>
</g>
        <rect x="37" y="341.9" class="st2" width="274" height="34.7"/>
        <g id="data-down">
	<text transform="matrix(1 0 0 1 258.6512 368.72)" class="st3 st4 st5">  {{smallDate(timeseries.ts[4])}}</text>
            <text transform="matrix(1 0 0 1 205.6042 368.72)" class="st3 st4 st5">{{smallDate(timeseries.ts[3])}}</text>
            <text transform="matrix(1 0 0 1 153.6678 368.72)" class="st3 st4 st5">{{smallDate(timeseries.ts[2])}}</text>
            <text transform="matrix(1 0 0 1 101.0775 368.72)" class="st3 st4 st5">{{smallDate(timeseries.ts[1])}}</text>
            <text transform="matrix(1 0 0 1 49.6913 368.72)" class="st3 st4 st5">{{smallDate(timeseries.ts[0])}}</text>
</g>
        <text transform="matrix(1 0 0 1 16.7938 345.1667)" class="st3 st4 st5">0</text>
        <text transform="matrix(1 0 0 1 15.3363 224.7671)" class="st3 st4 st5">15</text>
        <text transform="matrix(1 0 0 1 14.8082 264.9004)" class="st3 st4 st5">10</text>
        <text transform="matrix(1 0 0 1 17.3216 305.0337)" class="st3 st4 st5">5</text>
        <text transform="matrix(1 0 0 1 13.6917 184.6333)" class="st3 st4 st5">20</text>
        <text transform="matrix(1 0 0 1 14.1978 144.5)" class="st3 st4 st5">25</text>
        <line class="st6" x1="28" y1="342.2" x2="311" y2="342.2"/>
        <line class="st7" x1="24.7" y1="102" x2="307.7" y2="102"/>
        <line class="st6" x1="37" y1="354.2" x2="37" y2="124.8"/>
        <g id="data-top" class="animaSlideUp">
            <text id="main-date" transform="matrix(1 0 0 1 32.6665 18.0533)" class="st9 st4 st11">{{timeseries.ts[selectedDay]}}</text>
            <g><text transform="matrix(1 0 0 1 31.6999 63.3337)"><tspan x="0" y="0" class="st9 st10 st11">{{kiloToTons(timeseries.stock[selectedDay])}} </tspan><tspan x="4.3" y="15.8" class="st9 st4 st12">Tons</tspan></text></g>
            <g><text transform="matrix(1 0 0 1 31.6999 63.3337)"><tspan x="0" y="-20" class="st13">Stock</tspan></text></g>
            
            <g><text transform="matrix(1 0 0 1 104.5601 63.3335)"><tspan x="0" y="0" class="st9 st10 st11">{{kiloToTons(timeseries.dcr[selectedDay])}} </tspan><tspan x="8.1" y="15.8" class="st9 st4 st12">t/day</tspan></text></g>
            <g><text transform="matrix(1 0 0 1 104.5601 63.3335)"><tspan x="0" y="-20" class="st13">Consumption</tspan></text></g>
            
            <g><text transform="matrix(1 0 0 1 182.0051 63.3335)"><tspan x="0" y="0" class="st9 st10 st11 ">{{kiloToTons(timeseries.avg_dcr[selectedDay])}} </tspan><tspan x="8" y="15.8" class="st9 st4 st12">t/avg</tspan></text>	</g>
            <g><text transform="matrix(1 0 0 1 182.0051 63.3335)"><tspan x="0" y="-20" class="st13">Consumption Average</tspan></text></g>
            
            <g><text transform="matrix(1 0 0 1 274.281 63.3335)"><tspan x="0" y="0" class="st9 st10 st11">{{timeseries.eta[selectedDay]}}</tspan><tspan x="-4.1" y="15.8" class="st9 st4 st12">Day</tspan></text></g>
            <g><text transform="matrix(1 0 0 1 274.281 63.3335)"><tspan x="0" y="-20" class="st13">Remaining days</tspan></text></g>
        </g>
</svg>
</template>

<script>
    export default {
        name: "mainChart",
        data(){
            return {
                selectedDay: 4,
                valueTotal: 8.35,

            }
        },
        props:{
            timeseries: Object
        },

        methods:{

            kiloToTons(bigFloat){
                return (bigFloat/1000).toString().slice(0, 5);
            },

            smallDate(bigDate){
                return bigDate.slice(5);
            },
            selectDay(day){
                this.selectedDay = day;
            },

            convertTograph(numero){
                let maxTons = 25;
                let minTons = 0;
                let maxPathValue = 242;
                let minPathValue = 25;
                var refvalue = (maxPathValue-minPathValue)/(maxTons-minTons);

                return maxPathValue-(numero*refvalue);

            }

        }
    }
</script>

<style scoped>
    .st0{fill:none;stroke:#A8D1D3;stroke-width:12;stroke-miterlimit:10; stroke-linecap: round; stroke-dasharray: 242;}

    .st1{fill:none;stroke:#2D2E83;stroke-width:5;stroke-miterlimit:10; stroke-linecap: round; stroke-dasharray: 242;}
    .st2{fill:#FFFFFF;}
    .st3{fill:#352641;}
    .st4{font-family:'Montserrat';}
    .st5{font-size:11px;}
    .st6{fill:none;stroke:#A8D1D3;stroke-miterlimit:10;}
    .st7{fill:none;stroke:#D1D1D1;stroke-miterlimit:10;}
    .st8{fill:#A8D1D3;}
    .st9{fill:#2D2E83;}
    .st10{font-family:'Montserrat'; font-weight: 700}
    .st11{font-size:22px;}
    .st12{font-size:12px;}
    .st13{font-size:9px;}
    .clickable{
        cursor: pointer;
    }
</style>