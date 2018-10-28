<template>
    <div>
        <div class="header-abs" v-show='showAbs'>
            <router-link to='/' tag='div' class="iconfont header-abs-back">
                &#xe624;
            </router-link>
        </div>
        <div class="header-fixed" v-show='!showAbs' :style="opacityStyle">
            <router-link to="/">
                <div class="iconfont header-fixed-back-icon">&#xe624;</div>
                <div class="header-content">
                    页面详情
                </div>
            </router-link>
            
        </div> 
    </div>
    </div>

</template>

<script>
    export default {
        name: 'DetailHeader',
        data(){
            return{
                showAbs:true,
                opacityStyle:{
                    opacity:0
                }
            }
        },
        methods:{
            hanleScroll(){
             const top=document.documentElement.scrollTop;
             if(top>60){
                 let opacity=top/140;
                 opacity=opacity>1?1:opacity;
                 this.opacityStyle={opacity};
                 this.showAbs=false;
             }else{
                this.showAbs=true;
             }
            }
        },
        activated(){
            window.addEventListener('scroll',this.hanleScroll);
        }
    }
</script>
<style scoped>
    .header-abs {
        position: absolute;
        left: .4rem;
        top: .4rem;
        width: .8rem;
        height: .8rem;
        border-radius: .4rem;
        background-color: rgba(0, 0, 0, .8);
        text-align: center;
        line-height: .8rem;
    }
    .header-abs-back {
        font-size: .38rem;
        color: #fff;
    }
    .header-fixed {
        position: fixed;
        left: 0;
        top: 0;
        right: 0;
        height: .86rem;
        line-height: .86rem;
        text-align: center;
        color: #fff;
        font-size: .32rem;
        background-color: #00bcd4;
    }

    .header-fixed-back-icon {
        width: .64rem;
        height: 100%;
        color: #fff;
        position: absolute;
        left: 0;
        top: 0;
    }
    .header-content{
        color: #fff;
    }
</style>