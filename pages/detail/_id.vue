<template>
    <div class="detail-wrapper">
        <v-layout row wrap>
            <v-flex xs10 offset-xs1>
                <article class="detail-content text-xs-center">
                    <header class="detail-title text-xs-center">
                        Detail {{$route.params.id}}
                    </header>
                    <router-link :to="{
                        name: 'detailId',
                        params: {
                            id: Number($route.params.id) + 1
                        }
                    }">
                        请跳至 {{Number($route.params.id) + 1}}
                    </router-link>
                    <p>
                    渐进式Web应用程序是用户体验，具有Web的范围，并且：
可靠的负荷瞬间和永远的downasaur，即使在不确定的网络条件。
快速-快速响应用户的交互与流畅的动画和没有杰克滚动。
                    </p>
                </article>
            </v-flex>
        </v-layout>
    </div>
</template>

<script>
let state = {
    appHeaderState: {
        show: true,
        title: 'Lavas',
        showMenu: false,
        showBack: true,
        showLogo: false,
        actions: [
            {
                icon: 'home',
                route: {
                    name: 'index'
                }
            }
        ]
    }
};

function setState(store) {
    store.dispatch('appShell/appHeader/setAppHeader', state.appHeaderState);
}

export default {
    name: 'detail',
    metaInfo() {
        return {
            title: `路由 ${this.$route.params.id}`,
            titleTemplate: '%s - Lavas',
            meta: [
                {name: 'keywords', content: 'lavas PWA'},
                {name: 'description', content: '基于 Vue 的 PWA 解决方案，帮助开发者快速搭建 PWA 应用，解决接入 PWA 的各种问题'}
            ]
        }
    },
    async asyncData({store, route}) {
        setState(store);
        await new Promise((resolve, reject) => {
            setTimeout(resolve, 500);
        });
    },
    activated() {
        setState(this.$store);
    }
};
</script>

<style lang="stylus" scoped>

.detail-content
    font-size 16px
    line-height 30px
    margin-top 30px

    .detail-title
        margin-bottom 20px
        padding 10px 0
        font-size 36px
        font-weight bold

</style>
