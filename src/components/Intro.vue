<template>
    <div class="intro">
        <div class="info">
            <h1 class="info__title">ДОБРО ПОЖАЛОВАТЬ В НАШ НОВЫЙ МАГАЗИН!</h1>
            <p class="info__text">Мы садимся вязать, и вселенная вокруг начинает жить по-другому. Точнее, мы создаем 
               собственную вселенную, в которой мы отдыхаем, вдохновляемся и создаем шедевры. 
               Наш магазин за то, чтобы вы занимались своим любимым делом с удовольствием. Наш 
               магазин – это место, где вам предложат пряжу и инструмент исключительного качества 
               для создания лучших творений, которые вы только задумали. Наш магазин – это место, 
               куда вы просто можете прийти поболтать и выпить чашечку кофе за вязанием 
            </p>
            <a class="info__link" href="#">Узнать о нас больше</a>
        </div>
        <div class="intro__video">
           <iframe width="350" height="230" src="https://www.youtube.com/embed/cbSfIgyh8dA" title="YouTube video player" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture" allowfullscreen></iframe>
        </div>
    </div>
</template>

<style scoped>
.intro{
    margin: 10vh auto;
    max-width: 90%;
    display: flex;
    justify-content: space-evenly;
}
.info{
    position: relative;
    max-width: 540px;
    margin: 0 45px 0 0;
}
iframe{
    border: 2px solid #497952;
}
.info__link{
    position: absolute;
    color: #497952;
    text-align: end;
    right: 0;
    font-size: 12px;
    line-height: 13px;
}
.info__text{
    color: #535353;
    margin: 10px 0;
    font-size: 14px;
    line-height: 14px;
}
.info__title{
    color: #535353;
    font-size: 16px;
    line-height: 19px;
    font-weight: bold;
}
@media(max-width: 820px){
        .intro{
            margin: auto auto 20px auto;
            display: flex;
            flex-direction: column;
            align-items: center;
        }
        .info{
            max-width: 80%;
            margin: 15px 0;
        }
        .info__link{
            position: static;
            margin: 0 0 20px 0;
        }
    }
</style>