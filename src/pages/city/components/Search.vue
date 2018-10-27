<template>
    <div>
        <div class="search">
            <input type="text" placeholder="输入城市名或拼音" v-model="keyword">
        </div>
        <div class="search-content" ref="search" v-show="keyword">
            <ul>
                <li class="search-item border-bottom" v-for="item of list" :key="item.id">{{item.name}}</li>
                <li class="search-item border-bottom" v-show="hasList">没有找到匹配的项</li>
            </ul>
        </div>
    </div>
</template>

<script>
    import BScroll from 'better-scroll'
    export default {
        name: 'CitySearch',
        data() {
            return {
                list: [],
                isRun: false,
                keyword: ''
            }
        },
        computed:{
           hasList(){
               return !this.list.length
           }
        },
        mounted(){
            this.scroll = new BScroll(this.$refs.search);
        },
        props: {
            city: Object
        },
        watch: {
            keyword() {
                if(this.keyword==''){
                    this.list=[];
                    return;
                }
                if (this.isRun) {
                    return;
                } else {
                    this.isRun=true;
                     setTimeout(() => {
                        var result = [];
                        for (var key in this.city) {
                            var res = this.city[key];
                            res.forEach(element => {
                                if (element.name.indexOf(this.keyword) !== -1 || element.spell.indexOf(this.keyword) !== -1) {
                                    result.push(element);
                                }
                            });
                        }
                        this.list = result;
                        this.isRun=false;
                    }, 20)
                }
            }
        }
    }
</script>

<style scoped>
    .search {
        width: 100%;
        height: .72rem;
        background-color: #00bcd4;
        padding: 0 0.1rem;
    }

    input {
        box-sizing: border-box;
        width: 97%;
        border-radius: .06rem;
        padding: 0 0.1rem;
        height: .62rem;
        line-height: .62rem;
        text-align: center;
        color: #666;
    }

    .search-content {
        position: absolute;
        overflow: hidden;
        z-index: 1;
        top: 1.58rem;
        left: 0;
        right: 0;
        bottom: 0;
        background-color:#eee;
    }
    .search-item{
        line-height: .62rem;
        padding-left: .2rem;
        color:#666;
        background-color: #fff;
    }
</style>