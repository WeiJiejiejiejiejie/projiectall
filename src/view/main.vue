<template>
        <div>
            <mc-header></mc-header>
            <mc-footer></mc-footer>
            <router-view></router-view>


<!--            购物车   返回定顶部-->
        </div>
</template>

<script>
    import header from "./main/header";
    import footer from "./main/footer";
    export default {
        name: "vmain",
        components:{
            'mc-footer':footer,
            'mc-header':header
            // eslint-disable-next-line vue/no-unused-components
        }
    }
</script>

<style scoped>

</style>