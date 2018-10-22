<template>
    <div class="icons">
        <div class="icon">
            <img src="http://img1.qunarzz.com/piao/fusion/1611/54/ace00878a52d9702.png">
            <p>热门景点</p>
        </div>
        <div class="icon">
            <img src="http://img1.qunarzz.com/piao/fusion/1611/54/ace00878a52d9702.png">
            <p>热门景点</p>
        </div>
        <div class="icon">
            <img src="http://img1.qunarzz.com/piao/fusion/1611/54/ace00878a52d9702.png">
            <p>热门景点</p>
        </div>
        <div class="icon">
            <img src="http://img1.qunarzz.com/piao/fusion/1611/54/ace00878a52d9702.png">
            <p>热门景点</p>
        </div>
        <div class="icon">
            <img src="http://img1.qunarzz.com/piao/fusion/1611/54/ace00878a52d9702.png">
            <p>热门景点</p>
        </div>
        <div class="icon">
            <img src="http://img1.qunarzz.com/piao/fusion/1611/54/ace00878a52d9702.png">
            <p>热门景点</p>
        </div>
        <div class="icon">
            <img src="http://img1.qunarzz.com/piao/fusion/1611/54/ace00878a52d9702.png">
            <p>热门景点</p>
        </div>
        <div class="icon">
            <img src="http://img1.qunarzz.com/piao/fusion/1611/54/ace00878a52d9702.png">
            <p>热门景点</p>
        </div>
    </div>
</template>
<script>
    export default {
        name: "HomeIcon"
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