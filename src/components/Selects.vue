<template>
    <div @click="clicked" class="selects">
        {{name}}
    </div>
</template>

<script>
    export default {
        name: "Selects",
        props: ['name', 'id'],
        methods: {
            clicked() {
                this.$emit('clicked')
            }
        },


    }
</script>

<style scoped>
    .selects {
        background: white;
        padding: 30px;
        border: 1px solid #42b983;
        border-radius: 5px;
        max-width: 100%;
        font: 25px Arial, sans-serif;
        margin: 15px;
        cursor: pointer;

    }

   .selects:hover{
        background: rgb(116,205,165);

   }
    .selects:active{
        background: #42b983;
    }


</style>