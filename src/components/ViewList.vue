<template>
    <div class="viewList " >

        <div v-for="(product,index) in listArray" :key="index">

            <product-view :product="product" />

        </div>

        <Summary @payed="pay" :total="total"  class="footer"/>

    </div>
</template>

<script>

    import {EventBus} from "../event-bus/event-bus";
    import ProductView from "./ProductView";
    import Summary from "./Summary";

    export default {
        components: { Summary, ProductView},
        data(){
            return{
                listArray:[],


            }
        },
        name: "ViewList",
        methods: {
            pay(){
                this.listArray = []
                console.log('also working')
            }
        },
        computed:{
            total(){
                let sum = 0;
                for (let x = 0; x<this.listArray.length; x++){
                    sum = sum + this.listArray[x].count * this.listArray[x].cost
                }
                return sum;
            }
        },

        created() {

            EventBus.$on('sendArray', array =>{
                this.listArray = array


                // for(let i = 0; i<val.length; i++){
                //     let v = val[i]
                //     s = 1;
                //     for (let j = 0; j<val.length; j++){
                //         if(i==j) continue
                //         if (val[i]==val[j]){
                //             s++
                //
                //         }
                //
                //     }
                //
                // }
            })
        }
    }
</script>

<style scoped>

    .viewList{
        background: whitesmoke;
        width: 30%;
        min-height: 100%;
        float: left;
        text-align: center;
        margin: 5px;
        height: 400px;
        overflow-y: scroll;
    }
    .footer{
        width: 30%;
        position: fixed;
        right: 30px;
        bottom: 10px;
    }

</style>