<template>
  <div>
    <div class="header">
        <div class="header-left">
          <div class="iconfont back-icon">&#xe624;</div>
        </div>
        <div class="header-input">
          <span class="iconfont search-icon">&#xe681;</span>
          输入城市/景点/游玩主题
        </div>
        <router-link to='/city'>
          <div class="header-right">
            {{this.city}}
            <span class="iconfont">&#xe64a;</span>
          </div>
        </router-link>
      </div>
  </div>
</template>

<script>
// import { mapState } from 'vuex'
export default {
  name: 'HomeHeader',
  props:{
    city:String
  }
  // computed: {
  //   ...mapState(['city'])
  // }
}
</script>

<style lang="sass" rel="stylesheet/sass" scoped>
  .header
   display: flex
   line-height: .86rem
   background: #00bcd4
   color: #fff
   .header-left
    width: .64rem
    float: left
    .back-icon
      text-align: center
      font-size: .4rem
  .header-input
    flex: 1
    height: .64rem
    line-height: .64rem
    margin-top: .12rem
    margin-left: .2rem
    padding-left: .2rem
    background: #fff
    border-radius: .1rem
    color: #ccc
    .search-icon
     text-align:center
     font-size: .5rem
  .header-right
    min-width: 1.04rem
    padding: 0 .1rem
    float: right
    text-align: center
    color: #fff
    .arrow-icon
      margin-left: -.04rem
      font-size: .24rem
</style>
