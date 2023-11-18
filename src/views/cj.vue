<template>
    <el-button type="success" round class="but" @click="click1" >
    <p v-if="num%3==0">抽奖</p>
    <p v-else-if="num%3==1">抽奖中</p>
    <p v-else>中奖了</p>
    </el-button>
    <div>
        <img :src="show[count%total].order" alt="" id="tx">
    </div>
    <div v-if="num%3==2">
        <p id="hj">X等奖获奖者为</p>
        <img :src="show[count%total].order" alt="" id="big">
    </div>
    <dm/>
</template>

<script>
import { random } from "lodash";
import dm from "/src/views/dm.vue"
export default {
    data(){
        return{
        show:result,
        count:0,
        txt:"抽奖",
        num:0,
        tex:'',
        total:3,
    }},
    methods:{
        click1(event){
            this.num++;
            if (this.num%3==1){
                for (let i = 0; i < 30; i++) {
                    setTimeout(function () {
                    this.count=random(0,this.total-1);
                    }.bind(this), 100 * i)};
                setTimeout(function () {
                this.num++;
                }.bind(this), 2900)
            }}
        // 上面这是点击后抽奖的函数
    },
    components:{
        dm
    }
        // 弹幕组件
};
// 图片库
const result=[{
                "order": "/src/assets/images/宠物猫踢足球.png",
                "index":1
            },{
                "order": "/src/assets/images/逗狗宠物.png",
                "index":2
            },{
                "order": "/src/assets/images/溜狗狗.png",
                "index":3
            }];
</script>

<style>
#tx{
    width: 5vw;
    position: absolute;
    left: 47.5vw;
    bottom: 25vw;
}
#hj{
    font-size: xx-large;
    position: absolute;
    left: 32vw;
    bottom: 25vw;
}
#big{
    width: 10vw;
    position: absolute;
    left: 45vw;
    bottom: 22.5vw;
}
.but{
    width: 10vw;
    height: 5vw;
    border-radius: 5vw;
    position: absolute;
    left: 45vw;
    right: 45vw;
    bottom: 8vw;
    font-size: 2vw;
}
</style>