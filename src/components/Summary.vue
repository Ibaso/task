<template>
    <div>
        <div class="f">
            <div class="t1">Jami</div>
            <div class="t2">{{total}} so'm</div>
            <button @click="pay" class="button">
                To'lash
            </button>
        </div>
    </div>
</template>

<script>
    import {EventBus} from "../event-bus/event-bus";

    export default {
        methods: {
            pay() {
                if(this.total>0){
                if (confirm("To'lovni tasdiqlaysizmi?")) {
                    let empty = []
                    EventBus.$emit('payed', empty)
                }

            }
            }
        },

        name: "Summary",
        props: ['total']
    }
</script>

<style scoped>
    .f {
        background: rgb(18, 38, 63);
        border-radius: 5px;
        font: 20px Arial, sans-serif;
        color: white;
        height: 200px;
    }

    .t1 {
        float: left;
        margin: 20px;
        color: white;
    }

    .t2 {
        float: right;
        margin: 20px;
        color: white;
    }

    .button {
        color: white;
        border-radius: 5px;
        font: 20px Arial, sans-serif;
        text-align: center;
        width: 100px;
        height: 50px;
        background: forestgreen;
        position: fixed;
        right: 50px;
        bottom: 30px;
        border: none;
    }

</style>