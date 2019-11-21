<template>
    <div style="margin-top: -0.4rem">
    <van-nav-bar
            title="OFashion迷橙"
            left-text="返回"
            right-text="按钮"
            left-arrow
            @click-left="onClickLeft"
            @click-right="onClickRight"
    />
    <div class="goods">
        <van-swipe class="goods-swipe" :autoplay="3000">
            <van-swipe-item v-for="thumb in goods.goods_img_urls" :key="thumb">
                <img :src="thumb" >
            </van-swipe-item>
        </van-swipe>
        <van-cell-group>
            <van-cell>
                <div class="goods-title">{{ goods.title }}</div>
                <div class="goods-title">{{ goods.titlet }}</div>
                <div class="goods-price">{{ formatPrice(goods.price) }}</div>
                <div class="wei-goods-three"><span>收藏：{{goods.collect}}</span><span>已售出：{{goods.been_sold}}</span><span>买家秀：{{goods.buyer_show}}</span></div>
                <hr style="border: 0.005rem solid #ccc"/>
                <div class="wei-reduceprice"><span>优惠券</span><span>满5000减100</span><span>满3000减50</span><span><img src="../../public/assets/weiimg/common_arrow.png"></span></div>
                <hr style="border: 0.005rem solid #ccc"/>
                <div class="wei-goods-from">-商品来自于-</div>
                <div class="goods-title"><img src="https://img4.ofashion.com.cn/register/seller/20181218/566822817.042052.jpg?x-oss-process=image/resize,w_360/format,webp"/></div>
                <div class="goods-title" style="font-size: 0.14rem">{{ goods.store_name }}</div>
                <div class="wei-img-country"><img src="../../public/assets/weiimg/common_locationicon.png"/>中国</div>
                <div class="wei-goods-four">
                    <div>
                        <span>1242</span><br>
                        <span>全部宝贝</span>
                    </div>
                    <div>
                        <span>113</span><br>
                        <span>月内成交</span>
                    </div>
                    <div>
                        <span>243</span><br>
                        <span>粉丝</span>
                    </div>
                    <div>
                        <span>4.7</span><br>
                        <span>综合评分</span>
                    </div>

                </div>
                <div class="wei-goods-from">-商品详情-</div>
                <div class="goods-title">{{ goods.deal_note[0] }}</div>
                <div class="goods-title">{{ goods.deal_note[1] }}</div>
                <div class="wei-photo-every"><img :src="goods.goods_img_urls[0]"></div>
                <div class="wei-photo-every"><img :src="goods.goods_img_urls[1]"></div>
                <div class="wei-photo-every"><img :src="goods.goods_img_urls[2]"></div>
                <div class="wei-photo-every"><img :src="goods.goods_img_urls[3]"></div>
                <div class="wei-photo-every"><img :src="goods.goods_img_urls[4]"></div>
                <div class="wei-goods-from">-颜色规格-</div>
                <hr style="border: 0.005rem solid #ccc"/>
                <div class="wei-goods-color"><span style="margin-left: -0.7rem;">可选颜色</span><span style="margin-right: -0.3rem;">{{goods.select_color}}</span></div>
                <hr style="border: 0.005rem solid #ccc"/>
                <div class="wei-goods-color"><span style="margin-left: -0.54rem;">可选规格</span><span style="margin-right: -0.3rem;">{{formatSize(goods.select_size)}}</span></div>
                <hr style="border: 0.005rem solid #ccc"/>
                <div class="wei-goods-from">-物流信息-</div>
                <div class="wei-send-date">{{ goods.send_date }}</div>
                <div class="wei-send-cool"><img src="../../public/assets/weiimg/wei1.png"></div>
                <div class="wei-goods-color"><span style="margin-left: -0.7rem;">商品类型</span><span style="margin-right: -0.3rem;">{{goods.good_type}}</span></div>
                <hr style="border: 0.005rem solid #ccc"/>
                <div class="wei-goods-color"><span style="margin-left: -0.6rem;">商品价格</span><span style="margin-right: -0.3rem;">{{formatPrice(goods.price)}}</span></div>
                <hr style="border: 0.005rem solid #ccc"/>
                <div class="wei-goods-color"><span style="margin-left: -0.6rem;">运费</span><span style="margin-right: -0.3rem;">{{goods.freight}}</span></div>
                <hr style="border: 0.005rem solid #ccc"/>
                <div class="wei-goods-from">-品牌介绍-</div>
                <div class="wei-send-cool">{{goods.brand_introduce}}</div>
            </van-cell>
        </van-cell-group>


        <van-goods-action>
            <van-goods-action-icon icon="chat-o" @click="sorry">
                客服
            </van-goods-action-icon>
            <van-goods-action-icon icon="cart-o" @click="onClickCart">
                购物车
            </van-goods-action-icon>
            <van-goods-action-button type="warning" @click="sorry">
                加入购物车
            </van-goods-action-button>
            <van-goods-action-button type="danger" @click="sorry">
                立即购买
            </van-goods-action-button>
        </van-goods-action>
    </div>
    </div>
</template>

<script>
    import {
        NavBar,
        Tag,
        Col,
        Icon,
        Cell,
        CellGroup,
        Swipe,
        Toast,
        SwipeItem,
        GoodsAction,
        GoodsActionIcon,
        GoodsActionButton
    } from 'vant';
    export default {
        name: "detail",
        components: {
            [NavBar.name]: NavBar,
            [Tag.name]: Tag,
            [Col.name]: Col,
            [Icon.name]: Icon,
            [Cell.name]: Cell,
            [CellGroup.name]: CellGroup,
            [Swipe.name]: Swipe,
            [SwipeItem.name]: SwipeItem,
            [GoodsAction.name]: GoodsAction,
            [GoodsActionIcon.name]: GoodsActionIcon,
            [GoodsActionButton.name]: GoodsActionButton
        },
        data() {
            return {
                goods: {
                    "brand_introduce":" Moncler也是冬天想要美丽保暖的秘密之一，时尚的外形以及保暖性兼得让Moncler深受欢迎，Moncler名字就来自于Monestier de Clermon的缩写。是一家总部位于法国格勒诺布尔专门从事生产户外运动装备的*品牌。品牌Logo是M字母与一只公鸡的组合。Moncler品牌名来自于小镇Monestier de Clermon的缩写。Moncler的故事开始于第二次世界大战期间，品牌具有传奇历史，时至今日，Moncler在户外羽绒服业界中，成为首屈一指的国际顶尖品牌。 ",
                    "good_type":"现货",
                    "freight":"未知",
                    "send_date":"付款后5天内",
                    "select_color":"灰色",
                    "select_size":["M","X","XL","XXL"],
                    "deal_note":[
                        "1.物品在非真假问题时不做任何退换货",
                        "2.国内现货商品72小时内发出，默认顺丰到付"
                    ],
                    "store_name":"潮流买手店",
                    "collect":"133",
                    "been_sold":"9",
                    "buyer_show":"0",
                    title: 'VALENTINO',
                    titlet:'Rose同款 黑色徽标针织套衫',
                    price: 6330,
                    express: '免运费',
                    remain: 19,
                    "goods_img_urls": [
                        'https://img.ofashion.com.cn/public/goods/sale_quote/20191109/861342/41445dc5bb7e22b6d/5949324783666610_60585327.jpg?x-oss-process=image/resize,w_750/format,webp',
                        'https://img.ofashion.com.cn/public/goods/sale_quote/20191109/861342/12925dc5bb928e4ad/5949324988608280_82661370.jpg?x-oss-process=image/resize,w_750/format,webp',
                        'https://img.ofashion.com.cn/public/goods/sale_quote/20191109/861342/65405dc5bb83acaeb/5949324839930260_13828601.jpg?x-oss-process=image/resize,w_750/format,webp',
                        'https://img5.ofashion.com.cn/public/goods/sale_quote/20191109/861342/20245dc5bba6437b7/5949325185305330_81912721.jpg?x-oss-process=image/resize,w_750/format,webp',
                        'https://img4.ofashion.com.cn/public/goods/sale_quote/20191109/861342/66555dc5bb83902ab/5949324839733040_96857774.jpg?x-oss-process=image/resize,w_750/format,webp'
                    ]
                }
            };
        },
        methods: {
            formatPrice() {
                return '¥' + (this.goods.price ).toFixed(2);
            },
            formatSize(){
                return (this.goods.select_size).join(",")
            },
            onClickCart() {
                this.$router.push('cart');
            },
            sorry() {
                Toast('暂无后续逻辑~');
            }
        }
    };
</script>

<style lang="less">
    .goods {
        padding-bottom: 50px;
        &-swipe {
            img {
                width: 100%;
                display: block;
            }
        }
        &-title {
            font-size: 16px;
        }
        &-price {
            color: #f44;
        }
        &-express {
            color: #999;
            font-size: 12px;
            padding: 5px 15px;
        }
        &-cell-group {
            margin: 15px 0;
            .van-cell__value {
                color: #999;
            }
        }
        &-tag {
            margin-left: 5px;
        }
        .goods-swipe img{
            height: 3.6rem;
        }
        .goods-title{
            text-align: center;
        }
        .goods-price{
            text-align: center;
        }
        .wei-goods-three{
            text-align: center;
        }
        .wei-goods-three span{
            font-size: 0.1rem;
            padding: 0.1rem;
        }
       .goods-cell-group{
            margin-top: 0;
        }
        .wei-goods-from{
            width: 100%;
            margin: 0.13333rem auto 0;
            text-align: center;
            color: #333;
            font-size: 14px;
            background: #fff;
        }
        .goods-title img{
            width: 0.6rem;
            height: 0.6rem;
            margin: 0 auto;
            border-radius:0.8rem;
        }
        .wei-img-country{
            line-height: 0.2rem;
            width: 100%;
            text-align: center;
        }
        .wei-reduceprice{
            width: 100%;
            height: 0.4rem;
            line-height: 0.4rem;
        }
        .wei-reduceprice span:nth-child(1){
            float: left;
        }
        .wei-reduceprice span:nth-child(2){
            margin: 0 .11667rem 0 0;
            padding: 0.06667rem 0.26667rem;
            color: #fff;
            font-size: 12px;
            height: 0.3rem;
            background: #f71;

        }
        .wei-reduceprice span:nth-child(3){
            margin: 0 .11667rem 0 0;
            padding: 0.06667rem 0.26667rem;
            color: #fff;
            height: 0.3rem;
            font-size: 12px;
            background: #f71;
        }
        .wei-reduceprice span:nth-child(4) img{
            padding-top: 0.1rem;
            float: right;
        }
        .van-nav-bar__title{
            font-weight: 700;
        }
        .wei-goods-four{
            width: 90%;
            text-align: center;
            display: flex;
            margin: 0 auto;
            justify-content: space-around;
        }
        .wei-goods-four div{
            width: 25%;
            text-align: center;
        }
        .wei-goods-four div span:nth-child(1){
            color: orange;
        }
        .wei-photo-every{
            width: 100%;
            height: 3.25rem;
        }
        .wei-photo-every img{
            width: 100%;
            height: 100%;
        }
        .wei-goods-color{
            width: 100%;
            height: 0.48rem;
            display: flex;
            justify-content: space-around;
            line-height: 0.48rem;
        }
        .wei-send-date{
            width: 100%;
            height: 0.3rem;
            font-size: 0.12rem;
        }
        .wei-send-cool{
            width: 100%;
        }
        .wei-send-cool img{
            width: 100%;
        }

        clear:after{content:"";display:block;clear:both;height:0;overflow:hidden;visibility:hidden;}
    }
</style>
