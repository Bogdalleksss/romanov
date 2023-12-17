<template>
    <div
        class="finka-points__item"
        :class="{
            'finka-points__item_hovered': isHover,
            'finka-points__item_opened': isOpened,
        }"
    >
        <div class="finka-points__item--header">
            <div class="finka-points__item--number">{{ num }}</div>
            <div class="finka-points__item--title" v-html="title" />
        </div>
        <div class="finka-points__item--text" v-html="description"/>
        <div class="finka-points__item--cross" @click="$emit('close')">
            <svg class="icon icon-cross">
                <use xlink:href="~/assets/img/icons/symbol-defs.svg#icon-cross"></use>
            </svg>
        </div>
    </div>
</template>
<script>
export default {
    name: 'FinkaPointItem',
    props: {
        num: {
            type: Number,
            default: 1,
        },
        title: {
            type: String,
            default: ""
        },
        description: {
            type: String,
            default: ""
        },
        isHover: {
            type: Boolean,
            default: false,
        },
        isOpened: {
            type: Boolean,
            default: false,
        }
    },
}
</script>
<style lang="">
    
</style>