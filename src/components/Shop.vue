<template>
    <div class="shop">
        <div>
            <menu-select @changeType="changeType"/>
            <menu-products :type="type"/>
            <view-list/>
        </div>

    </div>
</template>

<script>

    import MenuSelect from "./MenuSelects";
    import MenuProducts from "./MenuProducts";
    import ViewList from "./ViewList";

    export default {

        name: "Shop",
        components: {ViewList, MenuProducts, MenuSelect},
        data() {
            return {
                type: 1
            }
        },
        methods: {
            changeType(val) {
                this.type = val

            }
        }

    }
</script>

<style scoped>
    .shop {
        background: whitesmoke;
        width: 100%;
        height: 100%;
    }

</style>