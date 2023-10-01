<script setup>

</script>

<template>
  <section class="greeting pt-lg-5">
    <div class="container">
      <div class="row">
        <div class="greeting_text col-lg-8 col-12 d-flex flex-column mt-4">
          <h3 class="mt-4">Дорогой друг, добро пожаловать! </h3>
          <p class="mt-3">Мы рады пригласить тебя окунуться в мир финансовой грамотности и сыграть в интеллектуальную игру «ФИНАНСОВЫЙ КОМПАС: навигация к успешному  будущему».</p>
          <p class="mt-2">
            Вас приветствует талисман регионального центра финансовой грамотности "Финикум" умная лисичка Фенечка!
            Фенечка - ваш проводник в увлекательном мире финансовой грамотности.
          </p>
        </div>
        <div class="col-lg-3 col-12 offset-lg-1 d-flex justify-content-end align-items-end">
          <img src="@/assets/greeting_img.png" class="img-fluid " alt="">
        </div>
      </div>
    </div>
  </section>
  <section class="benefit mt-4">
    <div class="container">
      <div class="row">
        <div class="benefit_img col-lg-5 d-flex justify-content-lg-start align-items-lg-start justify-content-center align-items-center">
          <img src="@/assets/benefit_img.png" class="img-fluid" alt="">
        </div>
        <div class="benefit_text col-lg-6 offset-lg-1 col-12 d-flex flex-column mt-3">
          <h3>Благодаря Фенечке вы:</h3>
          <div class="benefit_text__list mt-3">
            <div class="list_items d-flex flex-row justify-content-start align-items-start">
              <img src="@/assets/list_items_img.svg" alt="">
              <p>научитесь умело распоряжаться своим и семейным бюджетом;</p>
            </div>
            <div class="list_items d-flex flex-row justify-content-start align-items-start">
              <img src="@/assets/list_items_img.svg" alt="">
              <p>узнаете об одном из инструментов минимизации финансовых рисков - страховании;</p>
            </div>
            <div class="list_items d-flex flex-row justify-content-start align-items-start">
              <img src="@/assets/list_items_img.svg" alt="">
              <p>поймёте, почему важно уметь планировать расходы;</p>
            </div>
            <div class="list_items d-flex flex-row justify-content-start align-items-start">
              <img src="@/assets/list_items_img.svg" alt="">
              <p>узнаете как не оказаться обманутыми финансовыми мошенниками.</p>
            </div>
          </div>
        </div>

      </div>
    </div>
  </section>
</template>

<style scoped>
.greeting_text h3, .benefit_text h3{
  color: #283128;
  font-size: 35px;
  font-weight: 500;
  line-height: 35px;
}
.greeting_text p, .list_items p{
    color: #283128;
    font-size: 24px;
    font-weight: 400;
    line-height: 24px;
}
.list_items img{
    display: block;
    margin-top: 4px;
    margin-right: 16px;
}
@media (max-width: 992px){
    .greeting_text h3, .benefit_text h3{
        font-size: 25px;
        line-height: 25px;
    }
    .greeting_text p, .list_items p{
        font-size: 20px;
        line-height: 20px;
    }
    .img-fluid{
        width: 237px;
    }
    .benefit_img{
        order: 2;
    }
    .benefit_text{
        order: 1;
    }
}

@media (max-width: 576px){
    .greeting_text h3, .benefit_text h3{
        font-size: 18px;
        line-height: 22px;
    }
    .greeting_text p, .list_items p{
        font-size: 14px;
        line-height: 18px;
}
.img-fluid{
  width: 180px;
}
}
</style>