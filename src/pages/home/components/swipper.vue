<template>
    <div class="wrapper">
        <swiper :options="swiperOption">
            <swiper-slide v-for="item of swiperList" :key="item.id">
                <img class="swipper-img" :src="item.imgUrl">
            </swiper-slide>
            </swiper-slide>
            <div class="swiper-pagination" slot="pagination"></div>
        </swiper>
    </div>
</template>

<script>
    export default {
        name: 'HomeSwipper',
        data() {
            return {
                swiperOption: {
                    pagination: '.swiper-pagination',
                    loop:true
                },
                swiperList: [{
                        id:"0001",
                        imgUrl:"http://img1.qunarzz.com/piao/fusion/1809/a9/9cd909d4efc12a02.jpg_890x330_cdf2b8aa.jpg"
                    }, {
                        id:"0002",
                        imgUrl:"http://img1.qunarzz.com/piao/fusion/1809/f4/03da905b8b7d2202.jpg_890x330_afab380f.jpg"
                    }, {
                        id:"0003",
                        imgUrl:"http://img1.qunarzz.com/piao/fusion/1806/cf/eb8c2dfa395d7e02.jpg_890x330_e5cedf73.jpg"
                    }
                ]
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
        height: 31.25vw;
    }

    .wrapper .swipper-img {
        width: 100%;
    }
</style>