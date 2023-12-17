<template >
    <div class="reject">
        <div class="reject__inner">
            <div class="reject__title">Для посещения сайта
                <br>вам должно быть больше 18 лет.<br>
                Пожалуйста, покиньте страницу
            </div>
            <div class="reject__icon">
                <img src="~/assets/img/icons/agreement-decoaritve.svg" alt="decorative">
            </div>
        </div>
    </div>
</template>
<script>
export default {
    
}
</script>
<style>
    .reject  {
        position:fixed;
        z-index:1000;
        background:rgba(0,0,0,.9);
        left:0;
        top:0;
        right:0;
        bottom:0;
        justify-content:center
    }
    .reject ,.reject__inner {
        display:flex;
        flex-direction:column;
        align-items:center
    }
    
    .reject__inner {
        max-width:800px;
        width:100%;
        padding:50px 90px 60px;
        background:#fff;
        box-shadow:0 0 65px rgba(0,0,0,.15)
    }
    
    @media(max-width:1024px){
        .reject__inner {
            padding:30px 15px
        }
    }
    
    .reject__title {
        font-family:"Playfair Display",
        sans-serif;
        font-size:35px;
        line-height:50px;
        text-align:center;
        color:#000;
        margin-bottom:50px
    }
    
    @media(max-width:1024px) {
        .reject__title {
            margin-bottom:20px;
            font-size:20px;
            line-height:30px
        }
    }
    
    .reject__icon {
        margin-bottom:24px;
        max-width:445px;
        height:auto;
        width:calc(100% - 50px)
    }
    
    .reject__icon img {
        width:100%;
        height:auto
    }
</style>