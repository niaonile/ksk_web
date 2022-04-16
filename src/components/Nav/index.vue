<template>
    <div id="menu" :class="{isFixed: isFixed, navBox: true}">
        <div class="nav">
            <div :class="{tab: true}" v-for="(item, index) in navList" :key="index">
                <router-link :to="item.url">
                    {{ item.name }}
                </router-link>
            </div>
        </div>
    </div>
</template>

<script>
export default {
    computed: {
        active() {
            return this.$route.path
        },
    },
    data() {
        return {
            isFixed: false,
            navList: [
                {
                    url:'/index',
                    name: 'ホームページ'
                },
                { 
                    url:'/enterprise',
                    name: '企業情报'
                },
                { 
                    url:'/warehouse',
                    name: 'ロジスティクス'
                },
                {
                    url:'/business',
                    name: '主な事業内容'
                },
                { 
                    url:'/career',
                    name: '事業所案内'
                },
                { 
                    url:'/cooperation',
                    name: 'お問合せ'
                }
            ]
        }
    },
    mounted() {
        window.addEventListener('scroll', this.handleScroll);
    },
    destroyed () {
        window.removeEventListener('scroll', this.handleScroll)
    },
    methods: {
        handleScroll() {
            //计算滚动条位置
            let scrollTop = window.pageYOffset || document.documentElement.scrollTop || document.body.scrollTop;
            //计算绑定div位置
            let offsetTop = document.querySelector('#menu').offsetTop;
            //进行比较设置位置fixed
            this.isFixed = scrollTop > offsetTop;
            if (offsetTop === 0) this.isFixed = scrollTop > 94;
        },
    }
}
</script>

<style lang="scss" scoped>
.navBox {
    width: 100%;
    position: absolute;
    z-index: 99;
    background: rgb(101, 81, 168, .8);
    &.isFixed {
        position: fixed;
        top: 0;
    }
    .nav {
        width: 1200px;
        height: 70px;
        margin: 0 auto;
        color: #ffffff;
        font-size: 16px;
        font-weight: bolder;
        display: flex;
        justify-content: end;
        .tab {
            width: 180px;
            a {
                width: 100%;
                height: 100%;
                display: flex;
                align-items: center;
                justify-content: center;
                &.router-link-active {
                    background: rgb(255, 255, 255, .2);
                }
            }
            &:hover {
                background: rgb(255, 255, 255, .1);
            }
        }
    }
}
</style>