<template>
    <div>
        <banner :imgs='imgs' :sightName="sightName" :bannerImg="bannerImg"></banner>
        <detail-header></detail-header>
        <div class="container">
            <detail-list :list='list'></detail-list>
        </div>
    </div>

</template>

<script>
    import Banner from './components/Banner'
    import DetailHeader from './components/Header'
    import DetailList from './components/List'
    import axios from 'axios'
    export default {
        name: 'Detail',
        data() {
            return {
                list: [],
                imgs:[],
                sightName:"",
                bannerImg:""
            }
        },
        components: {
            Banner,
            DetailHeader,
            DetailList
        },
        methods:{
            getDetailInfo(){
                axios.get('/static/mock/detail.json',{
                    params:{
                        id:this.$route.params.id
                    }
                }).then(this.getDetailSucc);
            },
            getDetailSucc(res){
                res=res.data;
                if(res.ret&&res.data){
                    const data=res.data;
                    this.list=data.categoryList;
                    this.imgs=data.gallaryImgs;
                    this.sightName=data.sightName;
                    this.bannerImg=data.bannerImg;
                }
            }
        },
        mounted() {
         this.getDetailInfo();
        }
    }
</script>
<style scoped>
    .container {
        height: 50rem;
    }
</style>