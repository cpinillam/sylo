<template>
    <svg height="400" width="450">
        <path :style="total" class="cls-1" d="M35.91,173.66a108.2,108.2,0,0,1,91.65-155,108.23,108.23,0,0,1,102.84,60,109.8,109.8,0,0,1,10.44,61.16,108.69,108.69,0,0,1-9.91,33.86"/>

    </svg>
</template>

<script>
    export default {
        name: "lineBar",
        data () {
            return {
                valueTotal: 100,
                total: ""

            }
        },

        created() {
            this.total = "--stroke-dashoffset:" + this.valueTotal
        }


    }
</script>

<style lang="scss" scoped>

    .cls-1{
        fill:none;stroke:#4697aa;stroke-miterlimit:10;stroke-width:20px;
        stroke-dasharray: 450;
        stroke-linecap: round;
        stroke-dashoffset: var(--stroke-dashoffset);
    }
</style>