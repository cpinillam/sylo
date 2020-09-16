<template>
    <div class="MainHeader">
        <div class="MainHeader__nav-top">
            <btn-back></btn-back>
            <btn-config></btn-config>
        </div>
        <div class="MainHeader__title padding-horizontal">
            <div class="MainHeader__head">Stock levels</div>
            <div class="MainHeader__subhead">ID: 645645</div>
        </div>
        <div class="MainHeader__nav-bottom padding-horizontal">
            <btn-primary title="TODAY" @selecting="selectButton" :selected-button="selectedButton"></btn-primary>
            <btn-primary title="LAST 5 DAYS" @selecting="selectButton" :selected-button="selectedButton"></btn-primary>
        </div>

    </div>
</template>

<script>
    import BtnBack from "../../components/botons/btnBack";
    import BtnConfig from "../botons/btnConfig";
    import BtnPrimary from "../botons/btnPrimary";
    export default {
        name: "MainHeader",
        components: {BtnConfig, BtnBack, BtnPrimary},
        data (){
            return {
                selectedButton: "TODAY"
            }
        },
        methods:{
            selectButton(buttonista){
                this.selectedButton =  buttonista;
                this.$emit('selectinga', buttonista);
            }
        }
    }
</script>

<style lang="scss">
    .MainHeader {
        background-color: white;
        width: 100%;
        border-bottom-left-radius: 80px;
        padding: 20px;


        &__nav-top {
            width: 100%;
            display: flex;
            justify-content: space-between;

        }
        .padding-horizontal {
            padding-right: 10px;
            padding-left: 30px;
        }

        &__head {
            font-family: 'Montserrat';
            font-size: 26px;
            line-height: (30 / 26);
            font-weight: 700;
            letter-spacing: -0.01607154083251953em;
            color: #000;
        }

        &__subhead {
            font-family: 'Montserrat';
            font-size: 15px;
            line-height: (30 / 15);
            letter-spacing: -0.01607154083251953em;
            color: #000;
        }

        &__nav-bottom {
            padding-top: 20px;
            display: flex;
            flex-wrap: wrap;
            margin-bottom: 20px;
        }
            }
</style>
