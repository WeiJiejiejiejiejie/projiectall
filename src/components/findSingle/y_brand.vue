<template>
    <div>
<!--        最上面的查看更多品牌-->
        <div class="brand_title">
            <a href="#" class="title">
                <img src="../../../public/assets/images/findSingle/brand/brand_title.png" alt="">
                <span class="look_more">查看更多品牌&nbsp;>></span>
            </a>
        </div>
        <div class="adv_boss">
            <a href="#" v-for="(item,index) in 13" :key="index" class="adv">
                <img :src="`./assets/images/findSingle/brand/brand${index+1}.webp`" alt="">
            </a>
        </div>
    </div>
</template>

<script>
    export default {
        name: "y_brand"
    }
</script>

<style scoped>
.title{
    display: block;
    width: 100%;
    height: 0.6rem;
    position: relative;

}
.look_more{

    position: absolute;
    top: 0.2rem;
    right: 0.3rem;
    font-size: 0.13rem;
    z-index: 100;
}
.title img{
    width: 100%;
    height: 100%;
}


    .adv_boss{
        display: flex;
        justify-content: space-between;
        flex-wrap: wrap;
    }
    .adv{
        display:inline-block;
        width: 1.85rem;
        margin-top: 0.03rem;
        /*min-height: 1.04rem;*/
    }
    .adv img{
        width: 100%;
        height: 100%;
    }
</style>