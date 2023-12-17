<template lang="">
    <div class="finka-slider finka-content__slider">
        <div
            class="finka-slider__wrapper"
            v-swiper:mySwiper="swiperOption"
            ref="swiper"
        >
            <div class="swiper-wrapper">
                <div v-for="slide in slides"
                    :key="slide.id"
                    :class="{
                        'finka-slider__slide_opened': openedSlides.includes(slide.id)
                    }"
                    class="swiper-slide finka-slider__slide"
                >
                    <div class="finka-slider__slide--content">
                        <div class="finka-slider__slide--label">
                            finka
                        </div>
                        <div class="finka-slider__slide--title">
                            {{ slide.title }}
                        </div>
                        <div class="finka-slider__slide--text"><span>В составе</span> {{ slide.structure }}</div>
                        <div class="finka-slider__slide--text" v-html="slide.text"></div>
                        <div class="finka-slider__slide--list">
                            <div class="finka-slider__slide--item">
                                <span>Крепость:</span>
                                40% об.
                            </div>
                            <div class="finka-slider__slide--item">
                                <span>Объем:</span>
                                0,25 л, 0,5 л, 0,7 л
                            </div>
                        </div>
                        <div class="finka-slider__slide--more" @click="toggle(slide.id)">
                            {{ openedSlides.includes(slide.id) ? 'Скрыть' : 'Подробнее' }}
                        </div>
                    </div>
                    <div class="finka-slider__slide--image">
                        <img 
                            :src="require(`~/assets/img/finka/${slide.img}`)"
                            :alt="`Finka ${slide.title}`"
                        />
                    </div>
                </div>
            </div>
        </div>

        <div class="finka-slider__button_prev finka-slider__button " @click="prev">
            <svg class="icon icon-arrow"><use xlink:href="~/assets/img/icons/symbol-defs.svg#icon-arrow"></use></svg>
        </div>
        <div class="finka-slider__button_next finka-slider__button" @click="next">
            <svg class="icon icon-arrow"><use xlink:href="~/assets/img/icons/symbol-defs.svg#icon-arrow"></use></svg>
        </div>
    </div>
</template>
<script>

export default {
    name: "FinkaSlider",
    components: {},
    data() {
        return {
            slides: [
                {
                    id: 0,
                    title: "ОРИГИНАЛЬНАЯ",
                    structure: "премиальный пшеничный спирт, кристально чистая вода, сахарный сироп, мед натуральный, настои спиртованные клюквы и брусники.",
                    text: "<span>Своим насыщенным вкусом</span> водка FINKA обязана натуральным ингредиентам в составе. Вкус легкий, элегантный, раскрывается свежими тонами клюквы и брусники.",
                    img: "finka-original.png"
                },
                {
                    id: 1,
                    title: "Дикая морошка",
                    structure: "премиальный пшеничный спирт, кристально чистая вода, сахарный сироп, настой спиртованной морошки.",
                    text: "<span>Морошка</span> в составе придает водке гармоничный аромат и бархатисто мягкий, изысканный вкус.",
                    img: "finka-moroshka.png"
                },
                {
                    id: 2,
                    title: "Клюква",
                    structure: "премиальный пшеничный спирт, кристально чистая вода, сахарный сироп, спиртованный морс клюквы.",
                    text: "<span>Аромат</span> соткан из мягких, едва уловимых оттенков клюквы.",
                    img: "finka-klyukva.png"
                },
            ],
            openedSlides: [],
            swiperOption: {
                loop: true,
                slidesPerView: 1,
                navigation: {
                    Nextel: '.slider__button_next', // Next dom node
                    Prevel: '.slider__button_prev' // The previous page DOM node
                }
            },
        }
    },
    methods: {
        next() {
            this.mySwiper.slideNext();
        },
        prev() {
            this.mySwiper.slidePrev();
        },
        toggle(id) {
            const idx = this.openedSlides.findIndex(item => item === id);

            if (idx >= 0) this.openedSlides.splice(idx, 1);
            else this.openedSlides.push(id);
        },
    }
}
</script>
<style lang="">
    
</style>