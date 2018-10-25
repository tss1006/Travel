<template>
  <div class="search">
      <input type="text" placeholder="输入城市名或拼音">
  </div>
</template>

<script>
  export default{
      name:'CitySearch'
  }
</script>

<style scoped>
   .search{
       width: 100%;
       height: .72rem;
       background-color: #00bcd4; 
       padding: 0 0.1rem;
   }
   input{
       box-sizing: border-box;
       width: 97%;
       border-radius: .06rem;
       padding: 0 0.1rem;
       height: .62rem;
       line-height: .62rem;
       text-align: center;
       color:#666;
   }
</style>