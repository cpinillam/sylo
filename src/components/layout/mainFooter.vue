<template>
    <div class="mainFooter">
        <btn-cart></btn-cart>
    </div>
</template>

<script>
    import BtnCart from "../../components/botons/btnCart";

    export default {
        name: "mainFooter",
        components: {BtnCart}
    }
</script>

<style lang="scss" scoped>
    .mainFooter {
        display: flex;
        justify-content: center;
        position: fixed;
        bottom: 0;
        width: 100%;

    }
</style>