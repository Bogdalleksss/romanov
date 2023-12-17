<template>
    <div class="finka page page_warning page_bg">
        <div class="finka__wrapper">
            <div class="finka-intro animate">
                <div class="finka-intro__container container">
                    <div class="finka-intro__bottle">
                        <img src="~/assets/img/finka/bottle.png" alt="Finka bottle">
                    </div>
                    <div class="finka-intro__content">
                        <div class="finka-intro__title">
                            <span>От снежных лесов,</span>
                            <span>кристально чистых вод</span>
                            <span>и холодных зим.</span>
                        </div>
                        <div class="finka-intro__content--bottle">
                            <img src="~/assets/img/finka/bottle.png" alt="Finka bottle">
                        </div>
                        <div class="finka-intro__text">
                            Первозданная <span>природа Финляндии является</span>
                            идеальным <span>источником вдохновения</span>
                            для этой премиальной водки.

                        </div>
                    </div>
                    <div class="finka-intro__logo">
                        <img src="~/assets/img/finka/finka-logo.svg" alt="Finka">
                    </div>
                </div>
            </div>
            <div class="finka-content">
                <div class="finka-content__container container">
                    <div class="finka-advantages finka-content__advantages">
                        <div class="finka-advantages__item">
                            <div class="finka-advantages__item--title">
                                БЕЗУПРЕЧНОЕ<br>КАЧЕСТВО FINKA
                            </div>
                            <div class="finka-advantages__item--text">
                                рождается на одном из старейших на одном из старейших заводов России, история которого начинается с 1895 года. <br>Вековой опыт и следование классическим технологиям производства водки позволяет получать безупречное качество продукта.
                            </div>
                            <div class="finka-advantages__item--icon">
                                <svg class="icon icon-arrow">
                                    <use xlink:href="~/assets/img/icons/symbol-defs.svg#icon-arrow"></use>
                                </svg>
                            </div>
                        </div>
                        <div class="finka-advantages__item">
                            <div class="finka-advantages__item--title">
                                5-ступенчатая<br>фильтрация
                            </div>
                            <div class="finka-advantages__item--text">
                                с применением березового угля и насыщением ионами серебра серебра, а также на основе традиционных скандинавских рецептов водки, <br>
                                позволяет добиться эталонного мягкого вкуса  <br>и неповторимого сочетания с ягодами морошки, которую еще называют царской ягодой
                            </div>
                            <div class="finka-advantages__item--icon">
                                <svg class="icon icon-arrow">
                                    <use xlink:href="~/assets/img/icons/symbol-defs.svg#icon-arrow"></use>
                                </svg>
                            </div>
                        </div>
                        <div class="finka-advantages__item">
                            <div class="finka-advantages__item--title">Поддержание постоянно низкой температуры</div>
                            <div class="finka-advantages__item--text">и скорости фильтрации позволяет получать водку с высокими органолептическими показателями.</div>
                            <div class="finka-advantages__item--icon">
                                <svg class="icon icon-arrow">
                                    <use xlink:href="~/assets/img/icons/symbol-defs.svg#icon-arrow"></use>
                                </svg>
                            </div>
                        </div>
                    </div>
                    <div class="finka-content__inner">
                        <finka-slider />
                        <div class="finka-advantages finka-content__inner--advantages">
                            <div class="finka-advantages__item">
                                <div class="finka-advantages__item--title">
                                    БЕЗУПРЕЧНОЕ<br>КАЧЕСТВО FINKA
                                </div>
                                <div class="finka-advantages__item--text">
                                    рождается на одном из старейших на одном из старейших заводов России, история которого начинается с 1895 года. <br>Вековой опыт и следование классическим технологиям производства водки позволяет получать безупречное качество продукта.
                                </div>
                                <div class="finka-advantages__item--icon">
                                    <svg class="icon icon-arrow">
                                        <use xlink:href="~/assets/img/icons/symbol-defs.svg#icon-arrow"></use>
                                    </svg>
                                </div>
                            </div>
                            <div class="finka-advantages__item">
                                <div class="finka-advantages__item--title">
                                    5-ступенчатая<br>фильтрация
                                </div>
                                <div class="finka-advantages__item--text">
                                    с применением березового угля и насыщением ионами серебра серебра, а также на основе традиционных скандинавских рецептов водки, <br>
                                    позволяет добиться эталонного мягкого вкуса  <br>и неповторимого сочетания с ягодами морошки, которую еще называют царской ягодой
                                </div>
                                <div class="finka-advantages__item--icon">
                                    <svg class="icon icon-arrow">
                                        <use xlink:href="~/assets/img/icons/symbol-defs.svg#icon-arrow"></use>
                                    </svg>
                                </div>
                            </div>
                            <div class="finka-advantages__item">
                                <div class="finka-advantages__item--title">Поддержание постоянно низкой температуры</div>
                                <div class="finka-advantages__item--text">и скорости фильтрации позволяет получать водку с высокими органолептическими показателями.</div>
                                <div class="finka-advantages__item--icon">
                                    <svg class="icon icon-arrow">
                                        <use xlink:href="~/assets/img/icons/symbol-defs.svg#icon-arrow"></use>
                                    </svg>
                                </div>
                            </div>
                        </div>
                        <div class="finka-content__text">
                            <span>FINKA - превосходная мягкая водка</span>
                            в современном уникальном дизайне,<br>
                            <span>подчеркнет ваш прекрасный вкус.</span>
                        </div>
                    </div>
                </div>
            </div>
            <div class="finka-points">
                <div class="finka-points__container container">
                    <div class="finka-points__text">
                        <span>Дизайн</span>
                        , граничащий<br>с искусством
                    </div>
                    <div class="finka-points__bottle">
                        <img src="~/assets/img/finka/example.png" alt="Finka">
                        <div
                            v-for="item in 5"
                            :key="item"
                            class="finka-points__bottle--point"
                            :class="`finka-points__bottle--point_${item}`"
                            @mouseover="hoveredNum = item"
                            @mouseout="hoveredNum = 0"
                            @click="opendeNum = item"
                        >
                            {{ item }}
                        </div>
                    </div>
                    <div class="finka-points__list">
                        <finka-point-item
                            v-for="item in pointItems"
                            :key="item.num"
                            :num="item.num"
                            :title="item.title"
                            :description="item.description"
                            :isHover="hoveredNum === item.num"
                            :isOpened="opendeNum === item.num"
                            @close="opendeNum = 0"
                        />
                    </div>
                </div>
            </div>
            <div class="warning">Чрезмерное употребление алкоголя вредит вашему здоровью.</div>
        </div>
    </div>
</template>
<script>
export default {
    name: 'finka',
    transition() {
        if (!localStorage.fromTo) return 'slide-left';

        const { from, to } = JSON.parse(localStorage.fromTo);
        return to > from ? 'slide-left' : 'slide-right'
    },
    data() {
        return {
            pointItems: [
                {
                    num: 1,
                    title: "ИННОВАЦИОННАЯ <br> ТЕХНОЛОГИЯ УКУПОРКИ",
                    description: "Благодаря наличию рассекателя с гидродозатором обеспечивается контроль вскрытия."
                },
                {
                    num: 2,
                    title: "КЛАССИЧЕСКИЙ <br> СТИЛЬ",
                    description: "в дизайне этикетки обеспечивают свежесть, лаконичность, притягивают взгляды покупателей."
                },
                {
                    num: 3,
                    title: "ИЗЯЩНЫЙ <br> ВНЕШНИЙ ВИД",
                    description: "переплетается со сложнейшими инженерными решениями в дизайне бутылки"
                },
                {
                    num: 4,
                    title: "УТОЛЩЕНИЕ <br> СТЕКЛА",
                    description: "В горловой части придает бутылке особую изящность"
                },
                {
                    num: 5,
                    title: "ЭМБОССИНГ <br> В ВИДЕ БУКВЫ F",
                    description: "отлично дополняет дизайн бутылки, придает ей уникальности"
                },
            ],
            hoveredNum: 0,
            opendeNum: 0,
        }
    },
}
</script>
<style lang="">
    
</style>