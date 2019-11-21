<template>
    <div class="y-boss">
        <content-banner></content-banner>
    </div>
</template>

<script>
    import content_banner from "../../components/findSingle/content_banner";
    export default {
        name: "findSingle",
        components:{
            'content-banner':content_banner
        }
    }
</script>

<style scoped>
.y-boss{
    position: relative;
}
</style>