<template>
    <div class="container" @click="GalleryClickHandle">
        <div class="wrapper">
            <swiper :options="swiperOptions">
                <swiper-slide v-for="(item,index) in imgs" :key='index'>
                    <img class="gallery-img" :src="item">
                </swiper-slide>
                <div class="swiper-pagination" slot="pagination"></div>
            </swiper>
        </div>
    </div>
</template>

<script>
    export default {
        name: 'CommonGallery',
        props:{
            imgs:Array
        },
        methods:{
            GalleryClickHandle(){
                this.$emit('close');
            }
        },
        data(){
            return{
                swiperOptions:{
                    pagination:'.swiper-pagination',
                    paginationType:'fraction',
                    observeParents:true,
                    observer:true
                }
            }
            
        }
    }
</script>

<style scoped>
    .container>>>.swiper-container{
        overflow: inherit;
    }
    .container {
        z-index: 99;
        position: fixed;
        left: 0;
        right: 0;
        top: 0;
        bottom: 0;
        display: flex;
        flex-direction: column;
        justify-content: center;
        background: #000
    }

    .wrapper {
        height: 0;
        width: 100%;
        padding-bottom: 100%;
    }

    .gallery-img {
        width: 100%;
    }
    .swiper-pagination{
        color:#fff;
        bottom:-1rem;
    }
</style>