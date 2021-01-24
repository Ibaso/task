<template>
    <div class="product" >

        <div style="float: left; text-align: center; ">
            <img :src="product.url" height="70" width="80"/>
        </div>

        <div style="float: left;" >

            <div>{{product.name}}</div>
            <div>{{product.cost}} so'm</div>

        </div>

    </div>
</template>

<script>
    export default {
        name: "Product",
        props:{
            product: Object
        },
    }
</script>

<style scoped>
    .product{

        background: white;
        float: left;
        padding: 10px;
        border: 1px solid #42b983;
        border-radius: 5px;
        width: 45%;
        height: 60px;
        font: 20px Arial, sans-serif;
        margin: 5px;
    }

    .product:active{
        border: 1px solid black;
    }
</style>