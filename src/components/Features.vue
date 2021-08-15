<template>
    <div class="features">
        <div class="block block__one">
            <img src="./img/8.png" alt="">
            <p>Только натуральный состав</p>
        </div>
        <div class="block block__two">
            <img src="./img/9.png" alt="">
            <p>Актуальное наличие на сайте</p>
        </div>
        <div class="block block__three">
            <img src="./img/10.png" alt="">
            <p>Быстрая отправка</p>
        </div>
        <div class="block block__four">
            <img src="./img/11.png" alt="">
            <p>Удобное расположение</p>
        </div>
        <div class="block block__five">
            <img src="./img/12.png" alt="">
            <p>Помощь в подборе товаров</p>
        </div>
    </div>
</template>

<script>


</script>


<style scoped>
.features {
    margin: 7.5vh auto;
    max-width: 80%;
    display: flex;
    z-index: 1;
    justify-content: space-evenly;
    background: #fff;
}
.block {
    text-align: center;
    max-width: 132px;
    max-height: 148px;
}
.block p {
    color: #497952;
    font-weight: bold;
    margin: 19px 0;
}
@media(max-width: 730px) {
    .features {
        margin: 20px auto;
        z-index: 1;
        background: #fff;
        display: grid;
        grid-template-columns: 1fr 1fr;
        grid-gap: 8px;
    }
    .block {
        text-align: center;
        max-width: 120px;
        max-height: 148px;
        margin: 10px auto;
    }
    .block__five {
        grid-row: 3;
        grid-column: 1/-1;
        max-width: 240px;
        width: 240px;
        margin: 5px auto;
    }
}
</style>