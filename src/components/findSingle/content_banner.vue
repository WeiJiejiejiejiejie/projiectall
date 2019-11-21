<template>
    <div class="swiper-container y_swiper" >
        <div class="btn">
            <input type="text" class="swiper-button-prev y-swiper-button-prev y-swiper-button" readonly value="分类">
            <input type="text" class="swiper-button-next y-swiper-button-next y-swiper-button" readonly value="品牌">
        </div>
<!--        <div class="swiper-pagination one"></div>-->
        <div class="swiper-wrapper y_swiper-wrapper">

            <div class="swiper-slide box1" >
                <y-classify></y-classify>
            </div>
            <div class="swiper-slide box2"  >
                <y-brand></y-brand>
            </div>

        </div>
        <!--        分页器-->



<!--        < input class = "btn btn-gray swiper-button-prev" name = "" type = "button" value = "上一题" >-->
<!--        < input class = "btn btn-gray swiper-button-next" name = "" type = "button" value = "下一题" >-->

    </div>
</template>

<script>
    // eslint-disable-next-line no-undef
    import Swiper from "swiper";
    import y_classify from "./y_classify";
    import y_brand from "./y_brand";
    export default {
        name: "content_banner",
        components:{
            'y-classify':y_classify,
            'y-brand':y_brand
        },
        props:['data'],
        mounted() {
            this._initSwiper()
        },
        methods: {
            _initSwiper() {
                new Swiper(".y_swiper", {
                    // direction: "vertical",
                    // effect: "flip",
                    // 如果需要分页器


                    navigation: {
                        nextEl: '.swiper-button-next',
                        prevEl: '.swiper-button-prev',
                    },
                    pagination: {
                        el: ".swiper-pagination",
                        clickable :true,

                    },
                    observer:true,//修改swiper自己或子元素时，自动初始化swiper
                    observeParents:true//修改swiper的父元素时，自动初始化swiper
                })
            }
        }
    }

</script>

<style >
    @import "../../../node_modules/swiper/css/swiper.css";
.y_swiper {
    width: 100%;
    min-height: 1.85rem;
    margin-top: -0.1rem;
    /*给按钮留空间 */
    padding-top: 0.30rem;
    /*background-color: white;*/
    text-align: center;
    position: relative;
}
.box1 {
    min-height: 1.85rem;
    /*background-color: #42b983;*/
}

.box2 {
    min-height: 1.85rem;
    /*background-color: orange;*/
}
    /*改造分页器*/

.btn{
    position: absolute;
    width: 100%;
    top: 0;
}
.y-swiper-button{
    width: 50%;
    height: 0.3rem;
    text-align: center;
    margin: 0!important;
    border: none;
    border-bottom: 2px solid white;
    outline: none;
    color: black;

}
.y-swiper-button-prev{
    left: 0;
}
.y-swiper-button-next{
   right: 0;

}
.swiper-button-disabled{
    color: firebrick;
    border: none;
    border-bottom: 2px solid firebrick;
    background-color: white!important;

}
    .y_swiper-wrapper{
        margin-top: 0.03rem;
    }
</style>