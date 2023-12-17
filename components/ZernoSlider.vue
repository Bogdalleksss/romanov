<template lang="">
    <div class="slider__wrapper">
        <div
            class="slider"
            v-swiper:mySwiper="swiperOption"
            ref="swiper"
        >
            <div class="swiper-wrapper">
                    <div
                        v-for="slide in slides"
                        :key="slide.id"
                        :class="{
                            'zerno-slider__slide_opened': openedSlides.includes(slide.id)
                        }"
                        class="swiper-slide zerno-slider__slide"
                    >
                        <div  class="zerno-slider__slide--image">
                            <img 
                                :src="require(`~/assets/img/zerno/products/${slide.img}`)"
                                :alt="slide.title"
                            />
                        </div>
                        <div  class="zerno-slider__slide--content">
                            <div  class="zerno-slider__slide--title">
                                {{ slide.title }}
                            </div>
                            <div v-if="slide.subtitle" class="zerno-slider__slide--subtitle">
                                {{ slide.subtitle }}
                            </div>
                            <div  class="zerno-slider__slide--text">
                                {{ slide.text }}
                            </div>
                            <div  class="zerno-slider__slide--list">
                                <div  class="zerno-slider__slide--list-item">
                                    <span >Крепость:</span>
                                    {{ slide.strength }}% об.
                                </div>
                                <div  class="zerno-slider__slide--list-item">
                                    <span >Объем:</span>
                                    {{ slide.volume }} л
                                </div>
                            </div>
                            <div class="zerno-slider__slide--more" @click="toggle(slide.id)">
                                {{ openedSlides.includes(slide.id) ? 'Скрыть' : 'Подробнее' }}
                            </div>
                        </div>
                    </div>
            </div>
            <div class="slider__button_prev slider__button" @click="prev">
                <svg class="icon icon-arrow"><use xlink:href="~/assets/img/icons/symbol-defs.svg#icon-arrow"></use></svg>
            </div>
            <div class="slider__button_next slider__button" @click="next">
                <svg class="icon icon-arrow"><use xlink:href="~/assets/img/icons/symbol-defs.svg#icon-arrow"></use></svg>
            </div>
        </div>
    </div>
</template>
<script>

export default {
    name: "ZernoSlider",
    components: {},
    data() {
        return {
            slides: [
                {
                    id: 1,
                    title: "Натуральная Зерновая",
                    subtitle: "Флагман бренда.",
                    text: "Это классическая водка из отборного зерна пшеницы. В составе только высококачественный пшеничный спирт, кристально чистая вода, настои пшеничных сухарей и пшеницы. Благодаря сбалансированности компонентов напиток приобретает неповторимый мягкий вкус с легкой, присущей водке, горчинкой.",
                    strength: 40,
                    volume: "0,25 – 0,5 – 0,7 – 1,0",
                    img: "bottle1.png"
                },
                {
                    id: 2,
                    title: "Зерно Озимая",
                    subtitle: "",
                    text: "Отличительной особенностью продукта является присутствие в составе настоя озимой пшеницы. Благодаря длительному периоду созревания озимая пшеница превосходит другие зерновые культуры, что позволяет добиться свежести и мягкости во вкусе.",
                    strength: 40,
                    volume: "0,25 – 0,5 – 0,7 – 1,0",
                    img: "bottle2.png"
                },
                {
                    id: 3,
                    title: "Зерно Ржаная",
                    subtitle: "Отличное дополнение бренда вкусовой водкой.",
                    text: "Для придания напитку тонкого ржаного аромата и вкуса при купажировании используются ароматные спирты «Дарницкого» и «Бородинского» хлеба и настой ржи. Благодаря выверенному балансу используемых компонентов водке присуща определенная терпкость, незаметно переходящая в мягкое послевкусие со шлейфами ржи.",
                    strength: 40,
                    volume: "0,25 – 0,5 – 0,7 – 1,0",
                    img: "bottle3.png"
                },
                {
                    id: 0,
                    title: "Зерно Мёд и перец",
                    subtitle: "Настойка горькая занимает особое место в линейке бренда.",
                    text: "Продукт содержит в своем составе натуральные настои перца красного, перца душистого, перца черного, цветков липы, душицы и корицы. Приятную сладость напитку придают мед и сахарный сироп. Настойка отличается особым насыщенным ароматом и согревающим вкусом.",
                    strength: 35,
                    volume: "0,5",
                    img: "bottle4.png"
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