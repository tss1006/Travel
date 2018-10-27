<template>
   <div>
      <home-header></home-header>
     <home-swipper :list='SwipperList'></home-swipper>
     <home-icon :icon='iconList'></home-icon>
     <home-recommend :recommend='recommendList'></home-recommend>
     <home-weekend :weekend='weekendList'></home-weekend>
   </div>
</template>

<script>
import HomeHeader from './components/Header'
import HomeSwipper from './components/swipper'
import HomeIcon from './components/Icon'
import HomeRecommend from './components/recommend'
import HomeWeekend from './components/Weekend'
import axios from 'axios'
export default{
  name: 'Home',
  components: {
    HomeHeader,
    HomeSwipper,
    HomeIcon,
    HomeRecommend,
    HomeWeekend
  },
  data(){
    return {
      SwipperList:[],
      iconList:[],
      recommendList:[],
      weekendList:[],
      lastCity:''
    }
  },
  methods:{
    getHomeInfo(){
      axios.get('/static/mock/index.json?city='+this.$store.state.city)
      .then(this.getHomeInfoSucc)
    },
    getHomeInfoSucc(res){
        res=res.data;
        if(res.ret&&res.data){
          this.SwipperList=res.data.swiperList;
          this.iconList=res.data.iconList;
          this.recommendList=res.data.recommendList;
          this.weekendList=res.data.weekendList;
          }
    }
  },
  mounted(){
     this.getHomeInfo();
     this.lastCity=this.$store.state.city;
  },
  activated(){
    if(this.lastCity!==this.$store.state.city){
      this.lastCity=this.$store.state.city;
      this.getHomeInfo();
    }
  }
}
</script>

<style>
</style>
