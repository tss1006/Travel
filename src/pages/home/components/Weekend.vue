<template>
    <div>
        <div class="title">周末去哪儿</div>
        <ul>
            <li class="item border-bottom" v-for="item of weekend" :key="item.id">
                <div class="img-wrapper">
                    <img class="item-img" :src="item.imgUrl" />
                </div>

                <div class="item-info">
                    <p class="item-title">{{item.title}}</p>
                    <p class="item-desc">{{item.desc}}</p>
                </div>
            </li>
        </ul>
    </div>

</template>
<script>
    export default {
        name: "HomeWeekend",
        props:{
            weekend:Array
        }
    }
</script>
<style scoped>
    .title {
        margin-top: .2rem;
        line-height: .8rem;
        background: #eee;
        text-indent: .2rem;
    }

    .img-wrapper{
        width: 100%;
        height: 0;
        padding-bottom: 35%;
        overflow: hidden; 
    }
    .item-info {
        padding: .1rem;
        height: .66rem;
    }

    .item-info p {
        height: .30rem;
        line-height: .30rem;
        padding-top: .03rem;
    }
</style>