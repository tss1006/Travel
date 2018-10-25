<template>
    <div class="header">
        城市选择
        <router-link to="/">
           <div class="header-left">
            <div class="iconfont back-icon">&#xe624;</div>
        </div> 
        </router-link>       
    </div>
</template>

<script>
    export default {
        name: 'cityHeader'
    }
</script>

<style scoped>
    .header {
        width: 100%;
        height: .86rem;
        line-height: .86rem;
        text-align: center;
        color: #fff;
        font-size: .32rem;
        background-color: #00bcd4;
        position: relative;
    }

    .header-left {
        width: .64rem;
        height: 100%;
        color:#fff;
        position: absolute;
        left:0;
        top:0;
    }
</style>