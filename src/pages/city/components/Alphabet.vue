<template>
    <ul class="list">
        <li class="item">A</li>
        <li class="item">B</li>
        <li class="item">C</li>
        <li class="item">D</li>
    </ul>
</template>

<script>
    export default {
        name: 'CityAlphabet',
        mounted() {
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