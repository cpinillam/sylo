<template>
    <div class="btnCart">
        <i class="fas fa-shopping-cart">
        </i>
    </div>
</template>

<script>
    export default {
        name: "btnCart"
    }
</script>

<style lang="scss" scoped>
    @import "../../assets/scss/variables_colors";

    .btnCart {
        width: 62px;
        height: 62px;
        background: $main-mid;
        border-radius: 100%;
        margin: 40px;
        display: flex;
        justify-content: center;
        align-items: center;
        color: white;
        font-size: 1.5rem;
        font-weight: 100 !important;
        animation-name: animatedShadow;
        animation-duration: 2s;
        animation-iteration-count: infinite;
        animation-timing-function: linear;
        cursor: pointer;
        transition: all 0.2s;

        &:hover{
            transform: scale(1.1);
        }

    }

    @keyframes animatedShadow {
        0% {
            box-shadow: 0 0 0 0px rgba(79, 141, 203, 1), 0 0 0 15px rgba(79, 141, 203, 0.3), 0 0 0 30px rgba(79, 141, 203, 0.15);
        }

        100% {
            box-shadow: 0 0 0 15px rgba(79, 141, 203, 0.3), 0 0 0 30px rgba(79, 141, 203, 0.15), 0 0 0 40px rgba(79, 141, 203, 0);
        }
    }

</style>