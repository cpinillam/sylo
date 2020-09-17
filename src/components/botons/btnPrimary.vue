<template>
    <button class="btnPrimary" :class="{'active': isSelected}"  @click="select">
        {{title}}
    </button>
</template>

<script>
    export default {
        name: "btnPrimary",
        props: {
            title: {
                type: String,
                required:true
            },
            selectedButton: {
                type: String
            }
        },
        computed: {
          isSelected(){
              return this.title === this.selectedButton
          }
        },
        methods: {
            select(){
                this.$emit('selectButton', this.title)
            }
        }

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
        margin-right: 15px;
        text-transform: uppercase;
        font-family: 'Montserrat', sans-serif;
        font-size: 12px;
        line-height: (26 / 12);
        font-weight: 600;
        letter-spacing: 0.004em;
        transition: all 0.3s;


        &:hover {
            background: $main-mid;
            color: white;
        }


    }
    .active {
        background: $main-mid  !important;
        color: white;
    }

</style>


