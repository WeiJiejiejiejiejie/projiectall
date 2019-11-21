<template>
    <div class="header">
        <div class="first" v-show="'/main/home'===$route.path ?true:false">
            <div class="search"><img src="../../assets/images/header/search.png" alt=""></div>
            <div class="mid">logo</div>
            <div class="message">消息</div>
        </div>

        <div class=" second" v-show="'/main/chengQ'===$route.path ?true:false">
            <div class="search"><img src="../../assets/images/header/search.png" alt=""></div>
            <div class="message">消息</div>
        </div>
        <div class=" second " v-show="'/main/findsingle'===$route.path ?true:false">
            <div class="search findSearch">
                <find-single></find-single>
            </div>
            <div class="message">消息</div>
        </div>
        <div class=" second" v-show="'/main/mine'===$route.path ?true:false">
            <div class="search"><img src="../../assets/images/header/search.png" alt=""></div>
            <div class="message">消息</div>
        </div>
    </div>
</template>

<script>
    import findSingle_search from "../../components/findSingle/findSingle_search";
    export default {

        name: "vheader",
        components:{
            "find-single":findSingle_search
        }
    }
</script>

<style scoped>
.header{
    position: fixed;
    height: 0.3rem;
    width: 100%;
    top: 0;
    font-size: 0.24rem;
    z-index: 1000;
}
.first{
    display: flex;
    width: 100%;
    justify-content: space-around;
    height:100%;
    background-color: orangered;
}
.second{
    display: flex;
    width: 100%;
    justify-content: space-between;
    height: 100%;
    background-color: orangered;
}

.search{
    width: 20%;
    display: flex;
    align-items: center;
    justify-content: center;

}
.search img{
    width: 0.30rem;
    height: 0.30rem;
}
.findSearch{
    width: 80% !important;
    background-color: orange;
}
.mid{
    width: 60%;
    background-color: #42b983;
}
.message{
    width: 20%;
    background-color: firebrick;
}
</style>