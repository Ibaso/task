<template>
    <div class="menu" >
        <selects  @clicked="clicked(f.id)"  v-for="f in selectsArray" :name="f.name" :id="f.id" :key="f.id"  ></selects>
    </div>
</template>

<script>
    import Selects from "./Selects";
    export default {
        name: "MenuSelect",
        components: {Selects},
        methods:{
            clicked(id){
                this.$emit('clicked1',id)
            }
        },

        data(){
            return {

                selectsArray:[
                    {
                        id:1,
                        name:'Burgers'
                    },
                    {
                        id:2,
                        name:'Spinners'
                    },
                    {
                        id:3,
                        name:'Chicken'
                    },
                    {
                        id:4,
                        name:'Pizza'
                    },
                    {
                        id:5,
                        name:'Appetizers'
                    },

                ],
            }
        },

    }
</script>

<style scoped>
.menu{

    max-width: 16%;
    float: left;
    margin: 5px;
}
</style>