<template>
    <footer id="footer" :style="{backgroundColor: curMenu.bgColor}">
        <div v-for="obj in menuList" :key="obj.path" @click="changeMenu(obj)">
            <router-link :to="obj.path">{{obj.name}}</router-link>
        </div>

    </footer>
</template>

<script>
    import {mapState, mapMutations} from 'vuex'

    export default {
        data() {
            return {
                menuList: [{
                    path: '/',
                    name: '影视',
                    bgColor: '#ff0000'
                },
                    {
                        path: '/book',
                        name: '书籍',
                        bgColor: '#ff00ff'
                    },
                    {
                        path: '/music',
                        name: '音乐',
                        bgColor: '#cc0bd0'
                    },
                    {
                        path: '/chat',
                        name: '聊天',
                        bgColor: '#eeb090'
                    }
                ]
            }
        },
        computed: {
            ...mapState(['curMenu'])
        },
        methods: {
            ...mapMutations(['setcurMenu']),
            changeMenu(obj) {
                this.setcurMenu(obj)
            }
        }
    }
</script>

<style lang="scss" scoped>
    footer {display: flex;
        justify-content: space-around;
        position: fixed;
        bottom: 0;
        left: 0;
        width: 100%;
        height: 1rem;
        line-height: 1rem;
        text-align: center;
        background-color: red;
        color: white;
        a{
            color: white;
        }
        router-link-exact-active {
            color: #494949;
        }
    }
</style>