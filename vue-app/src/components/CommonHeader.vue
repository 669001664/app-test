<template>
    <header :style="{backgroundColor: curMenu.bgColor}">
        <span @click="gohome">首页</span>
        {{curMenu.name}}
    </header>
</template>

<script>
    import {mapMutations, mapState} from 'vuex'

    export default {
        name: "CommonHeader",
        computed: {
            ...mapState(['curMenu'])
        },
        methods: {
            ...mapMutations(['setcurMenu']),
            gohome() {
                this.$router.push('/')
                this.setcurMenu({
                    path: '/',
                    name: '影视',
                    bgColor: '#ff0000'
                })
            }
        }
    }
</script>

<style lang="scss" scoped>
    header {
        position: fixed;
        top: 0;
        left: 0;
        width: 100%;
        height: 1rem;
        line-height: 1rem;
        text-align: center;
        background-color: aqua;
        color: white;
        span {
            position: absolute;
            left: 0;
        }
    }
</style>