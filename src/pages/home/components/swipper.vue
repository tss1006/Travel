<template>
    <div class="wrapper">
        <swiper :options="swiperOption">
            <swiper-slide v-for="item of list" :key="item.id">
                <img class="swipper-img" :src="item.imgUrl">
            </swiper-slide>
            <div class="swiper-pagination" slot="pagination"></div>
        </swiper>
    </div>
</template>

<script>
    export default {
        name: 'HomeSwipper',
        props:{
            list:Array
        },
        data() {
            return {
                swiperOption: {
                    pagination: '.swiper-pagination',
                    loop:true
                }
            }
        }
    }
</script>
<style scoped>
    .wrapper>>>.swiper-pagination-bullet-active {
        background: #fff !important;
    }

    .wrapper {
        width: 100%;
        height: 0;
        overflow: hidden;
        padding-bottom: 37.08%;
    }

    .wrapper .swipper-img {
        width: 100%;
    }
</style>