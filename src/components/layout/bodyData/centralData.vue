<template>
    <div>
        <line-bar v-if="graph" :stock="stock" :max-capacity="maxCapacity" @click.native="selectView('viewSylo')"></line-bar>
        <sylo-svg v-else class="syloSvg" :status="status" @click.native="selectView('viewGraph')"></sylo-svg>
    </div>
</template>

<script>
    import SyloSvg from "../chart/syloSvg";
    import LineBar from "../chart/lineBar";

    export default {
        name: "centralData",
        components: {
            LineBar,
            SyloSvg,
        },
        props:{
            status: String,
            stock: Number,
            maxCapacity: Number,
            graph: Boolean
        },

        methods:{
            selectView(view){
                this.$emit('mainview', view)
            }
        }
    }
</script>

<style scoped>
    .syloSvg {
        width: 130px;
        margin-top: -40px;
        margin-bottom: -40px;
    }
</style>