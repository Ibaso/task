<template>
    <div class="menuProducts">
    <div @click="productSelector(index)" v-for="(product,index) in productsFilter" :key="index">
        <product   :product="product"   />

    </div>
    </div>
</template>

<script>
    import Product from "./Product";
    import {EventBus} from "../event-bus/event-bus";
    export default {
        name: "MenuProducts",
        components: {Product},
        props:{
            type:Number
        },
        methods:{
            productSelector(index){

                if(!this.selectedArray.includes(this.productsFilter[index])){
                    this.selectedArray.push(this.productsFilter[index])
                }
                this.selectedArray[this.selectedArray.indexOf(this.productsFilter[index])].count++
                EventBus.$emit('sendArray', this.selectedArray)
            }
        },
        created() {
            EventBus.$on('payed', array=>{
                this.selectedArray = array
                this.products.forEach(a=>{
                    a.count = 0
                })
            })
        },
        computed:{

            productsFilter(){
                let  val =[]

                this.products.forEach(v => {
                    if (v.type == this.type)
                        val.push(v)
                })

            return val
            }
        },

        data(){
            return {
                selectedArray: [],

                products:[
                    {
                        name:'Classic',
                        cost:14000,
                        type:1,
                        count:0,
                        url:'https://res.cloudinary.com/dthnjpsnk/image/upload/v1577256746/menu/burger/burger_classic.jpg'
                    },
                    {
                        name:'Bigger',
                        cost:19000,
                        type:1,
                        count:0,
                        url: 'https://res.cloudinary.com/dthnjpsnk/image/upload/v1577256746/menu/burger/burger_bigger.jpg',
                    },
                    {
                        name:'Loook',
                        cost:16000,
                        type:1,
                        count:0,
                        url: 'https://res.cloudinary.com/dthnjpsnk/image/upload/v1577256746/menu/burger/burger_loook.jpg',
                    },
                    {
                        name:'Cheeseburger',
                        cost:26000,
                        type:1,
                        count:0,
                        url: 'https://res.cloudinary.com/dthnjpsnk/image/upload/v1577256746/menu/burger/burger_cheese.jpg',
                    },
                    {
                        name:'Hamburger',
                        cost:23000,
                        type:1,
                        count:0,
                        url: 'https://res.cloudinary.com/dthnjpsnk/image/upload/v1577256746/menu/burger/burger_hamburger.jpg',
                    },
                    {
                        name:'Double Cheeseburger',
                        cost:39000,
                        type:1,
                        count:0,
                        url:'https://res.cloudinary.com/dthnjpsnk/image/upload/v1577256746/menu/burger/burger_doublecheese.jpg' ,
                    },
                    {
                        name:'Boss Burger',
                        cost:39000,
                        type:1,
                        count:0,
                        url: 'https://res.cloudinary.com/dthnjpsnk/image/upload/v1608367396/menu/burger/bossbur.jpg',
                    },
                    {
                        name:'Smile Box',
                        cost:16000,
                        type:2,
                        count:0,
                        url: 'https://res.cloudinary.com/dthnjpsnk/image/upload/v1577257483/menu/Spinner/spinner_smile_box.jpg',
                    },
                    {
                        name:'Duet Master',
                        cost:18000,
                        type:2,
                        count:0,
                        url: 'https://res.cloudinary.com/dthnjpsnk/image/upload/v1577257484/menu/Spinner/spinner_duet_master.jpg' ,
                    },
                    {
                        name:'Spinner',
                        cost:14000,
                        type:2,
                        count:0,
                        url:'https://res.cloudinary.com/dthnjpsnk/image/upload/v1577257483/menu/Spinner/spinner_wrap.jpg' ,
                    },
                    {
                        name:'Dinner Meal Normal',
                        cost:30000,
                        type:3,
                        count:0,
                        url: 'https://res.cloudinary.com/dthnjpsnk/image/upload/v1577256824/menu/Chickens/chicken_dinner_meal.jpg',
                    },
                    {
                        name:'Dinner Meal Spicy',
                        cost:30000,
                        type:3,
                        count:0,
                        url: 'https://res.cloudinary.com/dthnjpsnk/image/upload/v1577256824/menu/Chickens/chicken_dinner_meal.jpg',
                    },
                    {
                        name:'Snack Meal Normal',
                        cost:23000,
                        type:3,
                        count:0,
                        url: 'https://res.cloudinary.com/dthnjpsnk/image/upload/v1577256824/menu/Chickens/chicken_snack_meal.jpg',
                    },
                    {
                        name:'Snack Meal Spicy',
                        cost:23000,
                        type:3,
                        count:0,
                        url:'https://res.cloudinary.com/dthnjpsnk/image/upload/v1577256824/menu/Chickens/chicken_snack_meal.jpg' ,
                    },

                    {
                        name:'21 Pieces Chicken',
                        cost:120000,
                        type:3,
                        count:0,
                        url: 'https://res.cloudinary.com/dthnjpsnk/image/upload/v1577256825/menu/Chickens/chicken_bucket_21.jpg',
                    },
                    {
                        name:'Chicken 1 pcs',
                        cost:8000,
                        type:3,
                        count:0,
                        url:'https://res.cloudinary.com/dthnjpsnk/image/upload/v1577256824/menu/Chickens/chicken_piece.jpg' ,
                    },
                    {
                        name:'32 Pieces + 32 Wings',
                        cost:298000,
                        type:3,
                        count:0,
                        url: 'https://res.cloudinary.com/dthnjpsnk/image/upload/v1577256824/menu/Chickens/chicken_togora.jpg',
                    },
                    {
                        name:'Pizza Supreme',
                        cost:40000,
                        type:4,
                        count:0,
                        url: 'https://res.cloudinary.com/dthnjpsnk/image/upload/v1577257378/menu/Pizza/pizza_super_supreme.jpg',
                    },
                    {
                        name:'Pizza Vegan',
                        cost:29000,
                        type:4,
                        count:0,
                        url: 'https://res.cloudinary.com/dthnjpsnk/image/upload/v1577257378/menu/Pizza/pizza_vegetarian.jpg',
                    },
                    {
                        name:'Pizza Steak',
                        cost:49000,
                        type:4,
                        count:0,
                        url: 'https://res.cloudinary.com/dthnjpsnk/image/upload/v1577257377/menu/Pizza/pizza_steak.jpg',
                    },
                    {
                        name:'Pizza BBQ Chicken',
                        cost:49000,
                        type:4,
                        count:0,
                        url: 'https://res.cloudinary.com/dthnjpsnk/image/upload/v1577257379/menu/Pizza/pizza_bbq.jpg',
                    },
                    {
                        name:'Pepperoni',
                        cost:49000,
                        type:4,
                        count:0,
                        url: 'https://res.cloudinary.com/dthnjpsnk/image/upload/v1577257378/menu/Pizza/pizza_pepperoni.jpg',
                    },
                    {
                        name:'Hot wings',
                        cost:18000,
                        type:5,
                        count:0,
                        url: 'https://res.cloudinary.com/dthnjpsnk/image/upload/v1577256586/menu/Appetizer/appetizer_hot_wings.jpg',
                    },
                    {
                        name:'Strips',
                        cost:18000,
                        type:5,
                        count:0,
                        url: 'https://res.cloudinary.com/dthnjpsnk/image/upload/v1577256586/menu/appetizer/appetizer_strips.jpg',
                    },
                    {
                        name:'Bites',
                        cost:10000,
                        type:5,
                        count:0,
                        url: 'https://res.cloudinary.com/dthnjpsnk/image/upload/v1577256586/menu/appetizer/appetizer_bites.jpg' ,
                    },
                    {
                        name:'Mushrooms',
                        cost:9000,
                        type:5,
                        count:0,
                        url: 'https://res.cloudinary.com/dthnjpsnk/image/upload/v1577256586/menu/Appetizer/appetizer_mushroooms.jpg',
                    },
                    {
                        name:'Fries',
                        cost:9000,
                        type:5,
                        count:0,
                        url:'https://res.cloudinary.com/dthnjpsnk/image/upload/v1608446504/menu/appetizer/photo_2020-12-20_11-41-35.jpg' ,
                    },
                    {
                        name:'Cheese Nuggets',
                        cost:18000,
                        type:5,
                        count:0,
                        url: 'https://res.cloudinary.com/dthnjpsnk/image/upload/v1577256586/menu/Appetizer/appetizer_cheese_nuggets.jpg',
                    },
                ]
            }
        }
    }
</script>

<style scoped>
    .menuProducts{
        width: 56%;
        min-height: 100%;
        float: left;
        text-align: center;
        margin: 5px;
    }


</style>