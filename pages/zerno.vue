<template>
    <div class="zerno page page_bg page_warning">
        <div class="zerno-intro">
            <div class="cloud2"></div>
            <div class="cloud1"></div>
            <div class="cloud3"></div>
            <div class="cloud4"></div>
            <div class="bottle animate-fade"></div>
            <div class="zerno-intro__container container animate">
                <div class="zerno-intro__inner">
                    <div class="zerno-intro__title">
                        <div class="zerno-intro__logo">
                            <img src="~/assets/img/zerno/zerno-logo.svg" alt="Zerno">
                        </div>
                        <div class="zerno-intro__title--text">
                            Изготовлено <span>из 100%</span>
                            <br>зернового спирта

                        </div>
                    </div>
                    <div class="zerno-intro__text">Зерно  - классическая русская водка на премиальном пшеничном спирте</div>
                </div>
            </div>
        </div>
        <div class="zerno-advantages">
            <div class="zerno-advantages__container container animate">
                <div class="zerno-advantages__item zerno-advantages__item_1 zerno-advantages__item_active">
                    <svg class="icon icon-zerno-1">
                        <use xlink:href="~/assets/img/icons/symbol-defs.svg#icon-zerno-1"></use>
                    </svg>
                    <div class="zerno-advantages__item--text">Благодаря вековому опыту и классической технологии производства водки достигается бескомпромиссное качество продукта.</div>
                </div>
                <div class="zerno-advantages__item zerno-advantages__item_2">
                    <svg class="icon icon-zerno-2">
                        <use xlink:href="~/assets/img/icons/symbol-defs.svg#icon-zerno-2"></use>
                    </svg>
                    <div class="zerno-advantages__item--text">5-ступенчатая фильтрация с применением березового угля и насыщением ионами серебра позволяет добиться неповторимого мягкого вкуса водки.</div>
                </div>
                <div class="zerno-advantages__item zerno-advantages__item_3">
                    <svg class="icon icon-zerno-3">
                        <use xlink:href="~/assets/img/icons/symbol-defs.svg#icon-zerno-3"></use>
                    </svg>
                    <div class="zerno-advantages__item--text">Поддержание постоянно низкой температуры и скорости фильтрации позволяет получать водку с высокими органолептическими показателями.</div>
                </div>
            </div>
        </div>
        <div class="zerno-slider">
            <div class="container zerno-slider__container animate">
                <zerno-slider />
            </div>
        </div>
        <div class="zerno-bottle">
            <div class="zerno-bottle__container container animate">
                <div class="zerno-bottle__info">
                    <div class="zerno-bottle__info--title">Эффектная</div>
                    <div class="zerno-bottle__info--subtitle">Эксклюзивная бутылка</div>
                    <div class="zerno-bottle__info--bottle">
                        <img src="~/assets/img/zerno/products/bottle1.png" alt="Bottle">
                    </div>
                </div>
                <div class="zerno-bottle__content">
                    <div class="zerno-bottle__content--item">
                        <div class="zerno-bottle__cup">
                            <img src="~/assets/img/zerno/cup.png" alt="Cup">
                        </div>
                        <div class="zerno-bottle__content--text">
                            <div class="zerno-bottle__info--subtitle">Колпачок</div>
                            с контролем вскрытия и дозатором

                        </div>
                    </div>
                    <div class="zerno-bottle__content--item">
                        <div class="zerno-bottle__content--text">
                            <div class="zerno-bottle__info--subtitle">Уникальная многопозиционная</div>
                            геометрия этикетки

                        </div>
                        <div class="zerno-bottle__label">
                            <img src="~/assets/img/zerno/label.png" alt="Label">
                        </div>
                    </div>
                </div>
            </div>
        </div>
        <div class="warning">Чрезмерное употребление алкоголя вредит вашему здоровью.</div>
    </div>
</template>
<script>
export default {
    name: 'zerno',
    transition() {
        if (!localStorage.fromTo) return 'slide-left';

        const { from, to } = JSON.parse(localStorage.fromTo);
        return to > from ? 'slide-left' : 'slide-right'
    },
}
</script>
<style lang="">
    
</style>