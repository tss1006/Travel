<template>
    <div class="icons">
        <div class="icon" v-for="item of icon" :id='item.id'>
            <img :src=item.imgUrl>
            <p>{{item.desc}}</p>
        </div>
    </div>
</template>
<script>
    export default {
        name: "HomeIcon",
        props:{
            icon:Array
        }
    }
</script>
<style scoped>
    .icons {
        width: 100%;
        height: 50vw;
        display: flex;
        flex-wrap: wrap;
    }

    .icons .icon {
        width: 25%;
        height: 50%;
        display: flex;
        flex-direction: column;
        justify-content: center;
        align-items: center;
    }

    .icons .icon img {
        width: 70%;
        height: 85%;
    }

    .icons .icon p {
        display: block;
        text-align: center;
        font-size: 14px;
    }
</style>