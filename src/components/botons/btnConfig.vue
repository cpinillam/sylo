<template>
    <button  class="btnConfig">
        <i class="fas fas fa-list-ul"></i>
    </button>
</template>

<script>
    export default {
        name: "btnConfig"
    }
</script>


<style scoped lang="scss">
    .btnConfig {
        width: 40px;
        height: 40px;
        background: transparent;
        position: relative;
        cursor: pointer;
        font-size: 1.5rem;
        opacity: 0.5;

        i {
            position: absolute;
            left: 50%;
            top: 50%;
            transform: translate(-50%, -50%);
        }

        &:hover {
            opacity: 1;
        }

    }
</style>