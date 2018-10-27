<template>
    <ul class="list">
        <li class="item" v-for="(item,key) of city" :key="key">{{key}}</li>
        
    </ul>
</template>

<script>
    export default {
        name: 'CityAlphabet',
        props:{
            city:Object
        }
    }
</script>

<style scoped>
.list{
    position: absolute;
    top:1.58rem;
    right:0;
    bottom:0;
    width:.4rem;
    display: flex;
    flex-direction: column;
    justify-content: center;
}
.item{
    line-height: .4rem;
    text-align: center;
    color:#00bcd4;
}
</style>