<template>
    <ul class="list">
        <li class="item" v-for="item of letters" :key="item" :ref="item" @click="handle" @touchstart="handleTouchStart"
            @touchmove="handleTouchMove" @touchend="handleTouchEnd">
            {{item}}
        </li>
    </ul>
</template>

<script>
    export default {
        name: 'CityAlphabet',
        props: {
            city: Object
        },
        data() {
            return {
                touchStatus: false,
                startY: 0,
                isRun: false
            }
        },
        updated() {
            this.startY = this.$refs['A'][0].offsetTop;
        },
        computed: {
            letters() {
                let letters = [];
                for (var key in this.city) {
                    letters.push(key);
                }
                return letters;
            }
        },
        methods: {
            handle(e) {
                this.$emit('change', e.target.innerText);
            },
            handleTouchStart(e) {
                this.touchStatus = true;
            },
            handleTouchMove(e) {
                if (this.touchStatus) {
                    if (this.isRun) {
                        return;
                    } else {
                        this.isRun = true;
                        setTimeout(() => {
                            var touchY = e.touches[0].clientY - 79;
                            var index = Math.floor((touchY - this.startY) / 20);
                            if (index >= 0 && index <= this.letters.length) {
                                this.$emit('change', this.letters[index]);
                            }
                            this.isRun=false;
                        }, 30)
                    }

                }
            },
            handleTouchEnd(e) {
                this.touchStatus = false;
            }
        }
    }
</script>

<style scoped>
    .list {
        position: absolute;
        top: 1.58rem;
        right: 0;
        bottom: 0;
        width: .4rem;
        display: flex;
        flex-direction: column;
        justify-content: center;
    }

    .item {
        line-height: .4rem;
        text-align: center;
        color: #00bcd4;
    }
</style>