<template>
    <div class="boss">
        <div class="adv_boss">
            <a href="#" v-for="(item,index) in 6" :key="index" class="adv">
                <img :src="`./assets/images/findSingle/classify/classify${index+1}.webp`" alt="">
            </a>
        </div>
        <div class="hot_classify_boss">
            <div class="hot_classify">热门分类</div>
            <div class="hot_list">
                <div class="ht" v-for="(n,index) in 18" :key="index">
                    <img src="../../../public/assets/images/findSingle/classify/classify1.webp" alt="">
                    <span>运动休闲鞋</span>
                </div>
            </div>
        </div>
    </div>
</template>

<script>
    export default {
        name: "y_classify"
    }
</script>

<style scoped>
    .boss{
        background-color: white;
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

    /*----------------------*/
    .hot_classify_boss{
        position: relative;
    }
    .hot_classify{
        height: 0.4rem;
        line-height: 0.4rem;
/*border-bottom: 1px solid #cccccc;*/
    }
    .hot_classify:after{
         content: "";
         width: 0.8rem;
         height: 0.01rem;
         background-color: #cccccc;
         position: absolute;
         top: 0.2rem;
        right: 0.6rem;
     }
    .hot_classify:before{
        content: "";
        width: 0.8rem;
        height: 0.01rem;
        background-color: #cccccc;
        position: absolute;
        top: 0.2rem;
        left: 0.6rem;
    }
    .hot_list{
        display: flex;
        flex-wrap: wrap;
        justify-content: left;
    }
    .ht{
        width: 1.24rem;

    }
    .ht img{
        width: 100%;
        height: 1.25rem;
    }
</style>