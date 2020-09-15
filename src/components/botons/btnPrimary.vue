<template>
    <button class="btnPrimary">
        <div class="btnPrimary__text">TODAY</div>
    </button>
</template>

<script>
    export default {
        name: "btnPrimary"
    }
</script>

<style lang="scss">
    @import "../../assets/scss/variables_colors";

    .btnPrimary {
        display: flex;
        align-items: center;
        justify-content: center;
        padding-left: 15px;
        padding-right: 15px;
        border-radius: 30px;
        background: $gray-alpha;
        border: none;
        color: $gray-dark;
        outline:none !important;

        &:hover {
            background: $main-mid;
            color: white;
        }

        &:active {
            background: $main-mid;
        }

        &__text {
            font-family: 'Montserrat', sans-serif;
            font-size: 12px;
            line-height: (26 / 12);
            font-weight: 600;
            letter-spacing: 0.004em;




        }
    }

</style>


