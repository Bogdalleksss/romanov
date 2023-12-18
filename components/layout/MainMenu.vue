<template>
    <div class="app__menu">
        <nav
            ref="menu"
            class="menu"
            :class="{
                menu_fixed: isFixed
            }"
        >
            <div class="menu__container container">
                <ul class="menu__list">
                    <li
                        v-for="item in menu"
                        :key="item.id"
                        class="menu__item"
                        :class="getClassesForLink(item)"
                    >
                        <a
                            class="menu__link"
                            :class="{
                                'nuxt-link-active nuxt-link-exact-active':
                                    currentPath === item.route
                                    || item.subMenu && item.subMenu.find(el => el.route === currentPath)
                            }"
                            @click="$nuxt.$emit('to-page', item.route);"
                        >
                            {{ item.name }}
                        </a>

                        <ul
                            v-if="item.subMenu"
                            class="sub-menu"
                        >
                            <li
                                v-for="subItem in item.subMenu"
                                :key="subItem.id"
                            >
                            <a
                                class="sub-menu__link"
                                :class="{
                                    'nuxt-link-active nuxt-link-exact-active': currentPath === subItem.route
                                }"
                                @click="$nuxt.$emit('to-page', subItem.route);"
                            >
                                {{ subItem.name }}
                            </a>
                            </li>
                        </ul>
                    </li>
                    <li
                        class="menu__list--active"
                        :style="linkActiveOption"
                    />
                </ul>
            </div>
        </nav>
    </div>
</template>
<script>
export default {
    name: "MainMenu",
    props: {
        menu: {
            type: Array,
            default: () => []
        },
        allMenu: {
            type: Array,
            default: () => []
        },
        currentPath: {
            type: String,
            default: ""
        },
    },
    data() {
        return {
            linkActiveOption: {
                width: "350px",
                left: "50%",
            },
            isFixed: false,
            isInit: false,
            menuPos: 0,
        }
    },
    destroyed() {
        window.removeEventListener('scroll', this.scrollHandler);
    },
    computed: {

    },
    mounted() {
        // setTimeout(() => {
          this.setStyleActiveLink();
        // }, 50)
        setTimeout(() => this.isInit = true, 0)
        window.addEventListener('scroll', this.scrollHandler);
    },
    methods: {
        getClassesForLink({ route }) {
            const path = this.currentPath

            const currentLinkIndex = this.menu.findIndex(item => {
                let isSubItemActive = false;

                if (item.subMenu) {
                    isSubItemActive = item.subMenu.findIndex(el => el.route === path) >= 0;
                }

                return item.route === path || isSubItemActive;
            });

            if (currentLinkIndex < 0) return "";

            const currentLink = this.menu[currentLinkIndex];
            const prevLink = this.menu[currentLinkIndex - 1];
            const nextLink = this.menu[currentLinkIndex + 1];

            if (currentLink.route === route) return "menu__item_active";
            if (prevLink && prevLink.route === route) return "menu__item_before";
            if (nextLink && nextLink.route === route) return "menu__item_after";

            return "";
        },
        setStyleActiveLink() {
            setTimeout(() => {
                const menu = this.$refs.menu;
                const mainRoute = this.$route.path === '/';
                const { innerWidth } = window;
                const activeLink = menu.querySelector('.menu__item_active');
                const container = menu.querySelector('.menu__list');
                const { left, width } = activeLink.getBoundingClientRect();
                const diff = innerWidth - container.clientWidth;
                const centerPos = left - innerWidth / 2 - width / 2;
                const absPos = Math.abs(centerPos);
                const animationVector = (!mainRoute && !this.isInit) ? centerPos / absPos : 0;
                const animationDiff = 20 * animationVector

                this.linkActiveOption = {
                    width: `${activeLink.clientWidth + 90}px`,
                    left: `${left - diff / 2 - 45 - animationDiff}px`,
                }
            }, 0);
        },
        scrollHandler() {
            const { offsetTop } = this.$refs.menu;
            const { scrollY } = window;

            if (!this.isFixed) this.menuPos = offsetTop;

            this.isFixed = scrollY >= this.menuPos;
        },
    },
    watch: {
        $route() {
            this.setStyleActiveLink();
            delete localStorage.fromTo;
        },
        isFixed() {
            this.setStyleActiveLink();
        },
    },
}
</script>
<style lang="scss">
.app__menu {
    .menu {
        &__item {
            &:hover {
                .sub-menu {
                    opacity: 1;
                    top: 100%;
                }
            }
        }

        .sub-menu {
            position: absolute;
            display: grid;
            grid-template-columns: 1fr;
            width: 200%;
            top: 120%;
            padding-top: 30px;
            opacity: 0;
            transition: .4s;

            li {
                a {
                    width: 100%;
                    height: 100%;
                    text-align: center;
                    display: block;
                    padding: 15px;
                    transition: .4s;
                    background: #fff;

                    &:hover {
                        background: #000;
                        color: #fff;
                    }
                }
            }
        }
    }
}
</style>
