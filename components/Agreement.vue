<template>
    <div class="agreement">
            <div class="agreement__inner">
                <div class="agreement__title">
                    Для посещения сайта
                    <br>вам должно быть больше 18 лет.
                </div>
                <div class="agreement__icon">
                    <img src="~/assets/img/icons/agreement-decoaritve.svg" alt="decorative">
                </div>
                <div class="agreement__text">Вам исполнилось 18 лет?</div>
                <div class="agreement__buttons">
                    <button class="btn" @click="clickButton('y')">Да</button>
                    <button class="btn" @click="clickButton('n')">Нет</button>
                </div>
            </div>
        </div>      
</template>
<script>
export default {
    name: "Agreement",
    methods: {
        clickButton(value) {
            this.$emit('agreement-click', value)
        },
    },
}
</script>
<style lang="">
    
</style>