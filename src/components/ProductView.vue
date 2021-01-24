<template>
    <div class="productView" v-if="isExists" >



        <div style="float: left;" class="">

            <div>{{product.name}}</div>
            <div>{{total}} so'm  </div>

        </div>
        <div>

            <button @click="remove" class="button">-</button>
            <div style="float: right; padding-top: 13px">{{product.count}} ta</div>
            <button @click="add" class="button" >+</button>
        </div>
    </div>
</template>

<script>
    export default {
        name: "ProductView",
        props:{
            product: Object
        },
        computed:{
            total(){

                return this.product.cost * this.product.count
            },
            isExists(){
                if(this.product.count>0) return true
                else return false
            }
        },
        methods:{
            add(){

                this.product.count = this.product.count +1
            },
            remove(){
                if(this.product.count!=1) this.product.count = this.product.count -1
                else if(this.product.count==1){
                    this.product.count = this.product.count -1
                    this.bor = false
                }
            }
        },
        data(){
            return{
              bor: true
            }
        }
    }
</script>

<style scoped>
.productView{

    background: white;
    float: left;
    padding: 10px;
    border: 1px solid #42b983;
    border-radius: 5px;
    width: 90%;
    height: 60px;
    font: 20px Arial, sans-serif;
    margin: 5px;

}
    .button{
        margin: 5px;
        border: 1px solid #42b983 ;
        color: #42b983;
        background: white ;
        width: 40px;
        height: 40px;
        border-radius: 5px;
        font: 20px Arial, sans-serif;

        float: right
    }
</style>