<template>
    <div class="list" ref="wrapper">
        <div>
            <div class="area">
                <div class="title border-topbottom">当前城市</div>
                <div class="button-list">
                    <div class="button-wrap" >
                        <div class="button" @click='handle'>{{this.$store.state.city}}</div>
                    </div>
                </div>
            </div>
            <div class="area">
                <div class="title border-topbottom">热门城市</div>
                <div class="button-list">
                    <div class="button-wrap" v-for="item of hotcity" :key="item.id" @click='handleCityClick(item.name)'>
                        <div class="button" >{{item.name}}</div>
                    </div>
                </div>
                <div class="area" 
                     v-for="(value,key) of city" 
                     :key="key"
                     :ref="key"
                     >
                    <div class="title border-topbottom">{{key}}</div>
                    <div class="item-list">
                        <div class="item border-bottom" v-for="item of value" @click='handleCityClick(item.name)':key="item.id">{{item.name}}</div>
                    </div>
                </div>
            </div>
        </div>
    </div>

    </div>
</template>

<script>
    import BScroll from 'better-scroll'
    export default {
        name: 'CitySList',
        props: {
            city: Object,
            hotcity: Array,
            alphabet:String
        },
        mounted() {
            this.scroll = new BScroll(this.$refs.wrapper);
        },
        methods:{
            handleCityClick(city){
             this.$store.commit('changeCity',city);
             this.$router.push('/');
            },
            handle(){
                this.$router.push('/');
            }
        },
        watch:{
            alphabet(){
                if(this.alphabet){
                    const element=this.$refs[this.alphabet][0];
                    this.scroll.scrollToElement(element);
                }
            }
        }
    }
</script>

<style scoped>
    .list {
        overflow: hidden;
        position: absolute;
        top: 1.58rem;
        left: 0;
        right: 0;
        bottom: 0;
    }

    .title {
        line-height: .54rem;
        background-color: #eee;
        padding-left: .2rem;
        color: #666;
        font-size: .26rem;
    }

    .border-topbottom::before {
        border-color: #ccc;
    }

    .border-topbottom::after {
        border-color: #ccc;
    }

    .button-list {
        padding: .1rem .6rem .1rem .1rem;
        overflow: hidden;
    }

    .button-wrap {
        float: left;
        width: 33.33%;

    }

    .button {
        margin: .1rem;
        padding: .1rem 0;
        text-align: center;
        border: .02rem solid #ccc;
        border-radius: .06rem;
    }

    .item-list {
        line-height: .76rem;
        padding-left: .3rem;
    }

    .border-bottom::before {
        border-color: #ccc;
    }
</style>