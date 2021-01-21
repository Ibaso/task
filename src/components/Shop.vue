<template >
    <div class="shop" >

        <menu-select @clicked1="changeType"/>
        <menu-products :type="type"/>
        <view-list/>


    </div>
</template>

<script>

    import MenuSelect from "./MenuSelects";
    import MenuProducts from "./MenuProducts";
    import ViewList from "./ViewList";
    export default {

        name: "Shop",
        components: {ViewList, MenuProducts, MenuSelect},
        data(){
            return{
                type:1
            }
        },
        methods:{
            changeType(val){

                this.type = val

                 console.log(this.type)
            }
        }
        
    }
</script>

<style scoped>
    .shop{
        background: whitesmoke;
        width: 100% ;
        height: 100%;


    }

</style>