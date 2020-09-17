<template>
    <div class="btnDaysStock" :class="{'red': isRed}">
        <div class="btnDaysStock__icon">
            <i v-if="isRed" class="fas fa-exclamation-triangle">
            </i>
            <i v-else class="far fa-check-square">
            </i>
        </div>
        <div class="btnDaysStock__text">
            <div class="btnDaysStock__text__row">
                <div class="btnDaysStock__main-number">{{eta}}</div>
                <div class="btnDaysStock__titel">DAYS</div>
            </div>
            <div class="btnDaysStock__subtitel">of stock</div>
        </div>
    </div>
</template>

<script>
    export default {
        name: "btnDaysStock",
        props:{
            eta: Number,
            status: String
        },
        computed:{
            isRed(){
                return this.status === 'RED';
            }
        }
    }
</script>

<style lang="scss">
    @import "../../assets/scss/variables_colors";
    .red {
        background-color: #c55b5b !important;
    }

    .green {
        background-color: #5f9f1c;
    }

    .btnDaysStock {
        width: 247px;
        height: 78px;
        border-radius: 200px;
        display: flex;
        justify-content: center;
        align-items: center;
        color: $white;
        background-color: #5f9f1c;



        &__icon {
            width: 40%;
            text-align: center;
            i {
                font-size: 35px;
            }
        }

        &__text {
            width: 60%;
            font-family: 'Montserrat';
            display: flex;
            flex-direction: column;
            justify-content: left;
            text-align: left;

            &__row {
                display: flex;
                align-items: center;
            }
        }
        &__main-number {
            font-size: 42px;
            line-height: 90% ;
            font-weight: 700;
        }

        &__titel {
            font-size: 18px !important;
            font-weight: 300;
            margin-left: 5px;
        }

        &__subtitel {
            font-size: 11px !important;
        }


    }
</style>
