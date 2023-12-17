<template>
    <div
        :data-number="num"
        :class="{
            'romanov-advantages__item_active': isHover
        }"
        class="romanov-advantages__item"
        @mouseover="toggle"
        @mouseout="toggle"
    >
        <div class="romanov-advantages__item--closer" @click="isHover = false">
            <svg class="icon icon-cross">
                <use xlink:href="~/assets/img/icons/symbol-defs.svg#icon-cross"></use>
            </svg>
        </div>
        <div class="romanov-advantages__item--number">{{ num }}</div>
        <div
            class="romanov-advantages__item--content"
            :class="{
                'romanov-advantages__item--content_horizontal': num === 5,
            }"
        >
            <div class="romanov-advantages__item--text" v-html="text" />
            <div class="romanov-advantages__item--image">
                <img :src="require(`~/assets/img/romanov/advantages/advantage${num}.${num != 3 ? 'png' : 'svg'}`)" :alt="text">
            </div>
        </div>
    </div>
</template>
<script>
export default {
    name: "advantage",
    props: {
        text: {
            type: String,
            default: "",
        },
        num: {
            type: Number,
            default: 1,
        },
        mobileNum: {
            type: Number,
            default: 0,
        }
    },
    data() {
        return {
            isHover: false,
            isMobile: false
        }
    },
    mounted() {
        window.addEventListener('resize', this.resizeHandler);
        this.resizeHandler();
    },
    destroyed() {
        window.removeEventListener('resize', this.resizeHandler);
    },
    methods: {
        toggle() {
            if (!this.isMobile) {
                this.isHover = !this.isHover;
                this.$emit('toggle');
            }
        },
        resizeHandler() {
            this.isMobile = window.innerWidth <= 1024;
        },
    },
    watch: {
        mobileNum() {
            if (this.mobileNum === this.num) this.isHover = true
            else this.isHover = false
        },
    },
}
</script>
<style lang="">
    
</style>