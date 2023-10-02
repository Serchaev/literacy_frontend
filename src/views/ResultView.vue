<script>

import router from "@/router";

export default {
  methods: {
    router() {
      return router
    }
  },
  data(){
    return {
      percents: 0
    }
  },
  props: {
    result: {
      type: Number,
      required: true
    }
  },
  mounted() {
    this.percents = Math.floor(this.result * 100 / 3000)
  }
}

</script>

<template>
  <div class="results pb-5 mb-5">
    <div class="green">
      <div class="container">
        <img src="@/assets/result_green_img.png" alt="" class="result_green_img">
        <img src="@/assets/result_green_img__mini.png" alt="" class="result_green_img__mini">
      </div>

    </div>
    <div class="container">
      <div class="row">
        <div class="result">
          У Вас <div class="result_percent">{{ this.percents }}%</div> правильных ответов
        </div>
      </div>
      <div class="row">
        <div class="col-md-10 offset-md-1 description">
          <p class="desk_base text-center" v-if="this.percents >= 75">
            Вы отлично ориентируетесь в огромном море финансовых и кредитных отношений, вас не пугают достаточно сложные вопросы и неоднозначные ситуации!
          </p>
          <p class="desk_base text-center" v-else-if="this.percents >= 50">
            Вы неплохо знакомы с миром финансовых и кредитных отношений! Вы знаете свои права как потребителя товаров и услуг!
          </p>
          <p class="desk_base text-center" v-else>
            Вам необходимо продолжить увлекательное путешествие в мир финансовой грамотности для того, чтобы уверенно ориентироваться в нем и избежать финансовых ловушек!
          </p>
        </div>
      </div>
    </div>
    <div class="container recommendations">
      <div class="container_left">
        <h3 class="desk_h3">Желаете повысить свои знания в теме финансовой грамотности?</h3>
        <p class="desk_base d-block">Советуем посетить следующие источники:</p>


        <div class="hrefs" v-if="this.percents<25">
          <div class="hrefs_item mt-2">
            <img src="@/assets/hrefs_item_img.png" alt="">
            <a href="https://fincult.info/upload/iblock/ff6/ff6152774da48d2b2e3d22d0f4a28a34.pdf" class="desk_base d-block">Зачем быть финансово грамотным?</a>
          </div>
          <div class="hrefs_item mt-2">
            <img src="@/assets/hrefs_item_img.png" alt="">
            <a href="https://fincult.info/upload/iblock/a37/a373cee8527ec96d8c092c42c0a81e6f.pdf" class="desk_base d-block">Мой первый финансовый план, как подростку накопить на мечту</a>
          </div>
          <div class="hrefs_item mt-2">
            <img src="@/assets/hrefs_item_img.png" alt="">
            <a href="https://fincult.info/upload/iblock/154/CB_Brochure_Money_internet.pdf" class="desk_base d-block">Деньги: откуда они берутся и кто их контролирует</a>
          </div>
          <div class="hrefs_item mt-2">
            <img src="@/assets/hrefs_item_img.png" alt="">
            <a href="https://моифинансы.рф/article/chto-takoe-inflyaciya-i-kak-zashitit-ot-nee-svoi-dengi/" class="desk_base d-block">Что такое инфляция и как защитить от нее свои деньги</a>
          </div>
          <div class="hrefs_item mt-2">
            <img src="@/assets/hrefs_item_img.png" alt="">
            <a href="https://моифинансы.рф/landing/guide/" class="desk_base d-block">Учебник по финансовой грамотности</a>
          </div>
        </div>


        <div class="hrefs" v-else-if="this.percents<50">
          <div class="hrefs_item mt-2">
            <img src="@/assets/hrefs_item_img.png" alt="">
            <a href="https://fincult.info/upload/iblock/ff6/ff6152774da48d2b2e3d22d0f4a28a34.pdf" class="desk_base d-block">Зачем быть финансово грамотным?</a>
          </div>
          <div class="hrefs_item mt-2">
            <img src="@/assets/hrefs_item_img.png" alt="">
            <a href="https://моифинансы.рф/article/15-voprosov-dlya-proverki-finansovoj-gramotnosti/" class="desk_base d-block">15 важных вопросов для проверки финансовой грамотности</a>
          </div>
          <div class="hrefs_item mt-2">
            <img src="@/assets/hrefs_item_img.png" alt="">
            <a href="https://fincult.info/upload/iblock/154/CB_Brochure_Money_internet.pdf" class="desk_base d-block">Деньги: откуда они берутся и кто их контролирует</a>
          </div>
          <div class="hrefs_item mt-2">
            <img src="@/assets/hrefs_item_img.png" alt="">
            <a href="https://fincult.info/upload/iblock/4a7/4a73954b7741edce75997b8ddfcae6b4.pdf" class="desk_base d-block">Инфляция: что это такое и от чего она зависит</a>
          </div>
          <div class="hrefs_item mt-2">
            <img src="@/assets/hrefs_item_img.png" alt="">
            <a href="https://моифинансы.рф/landing/guide/" class="desk_base d-block">Учебник по финансовой грамотности</a>
          </div>
        </div>


        <div class="hrefs" v-else-if="this.percents<75">
          <div class="hrefs_item mt-2">
            <img src="@/assets/hrefs_item_img.png" alt="">
            <a href="https://моифинансы.рф/article/15-voprosov-dlya-proverki-finansovoj-gramotnosti/" class="desk_base d-block">15 важных вопросов для проверки финансовой грамотности</a>
          </div>
          <div class="hrefs_item mt-2">
            <img src="@/assets/hrefs_item_img.png" alt="">
            <a href="https://fincult.info/upload/iblock/5fc/5fccba43e8498947632e3ef67f91e297.pdf" class="desk_base d-block">Все о курсе валют</a>
          </div>
          <div class="hrefs_item mt-2">
            <img src="@/assets/hrefs_item_img.png" alt="">
            <a href="https://моифинансы.рф/article/bankovskij-vklad-nakopitelnyj-schet-i-karty-s-procentom-na-ostatok:-v-chem-raznica/" class="desk_base d-block">Банковский вклад, накопительный счет и карты с процентом на остаток: в чем разница?</a>
          </div>
          <div class="hrefs_item mt-2">
            <img src="@/assets/hrefs_item_img.png" alt="">
            <a href="https://fincult.info/upload/iblock/4a7/4a73954b7741edce75997b8ddfcae6b4.pdf" class="desk_base d-block">Инфляция: что это такое и от чего она зависит</a>
          </div>
          <div class="hrefs_item mt-2">
            <img src="@/assets/hrefs_item_img.png" alt="">
            <a href="https://моифинансы.рф/landing/guide/" class="desk_base d-block">Учебник по финансовой грамотности</a>
          </div>
        </div>


        <div class="hrefs" v-else>
          <div class="hrefs_item mt-2">
            <img src="@/assets/hrefs_item_img.png" alt="">
            <a href="https://fincult.info/upload/iblock/326/326d08f23ba151d0c9ad0fff1cd88af1.pdf" class="desk_base d-block">Кредиты и займы, какие они бывают</a>
          </div>
          <div class="hrefs_item mt-2">
            <img src="@/assets/hrefs_item_img.png" alt="">
            <a href="https://fincult.info/upload/iblock/088/CBR_Presentation_new_investor.pdf" class="desk_base d-block">Начинающий инвестор: что нужно знать о торговле на бирже</a>
          </div>
          <div class="hrefs_item mt-2">
            <img src="@/assets/hrefs_item_img.png" alt="">
            <a href="https://моифинансы.рф/article/slozhnyj-procent-v-nakopleniyah:-kak-eto-rabotaet/" class="desk_base d-block">Сложный процент в накоплениях: как это работает</a>
          </div>
          <div class="hrefs_item mt-2">
            <img src="@/assets/hrefs_item_img.png" alt="">
            <a href="https://моифинансы.рф/landing/wheel_life/" class="desk_base d-block">Трекер финансового здоровья</a>
          </div>
          <div class="hrefs_item mt-2">
            <img src="@/assets/hrefs_item_img.png" alt="">
            <a href="https://моифинансы.рф/landing/guide/" class="desk_base d-block">Учебник по финансовой грамотности</a>
          </div>
        </div>


      </div>
      <div class="container_right">
        <img src="@/assets/container_right_img.png" alt="">
      </div>
    </div>
    <div class="container d-flex justify-content-center">
      <button class="next" type="button" @click="$router.push('/')">
        На главную
      </button>
    </div>
  </div>
</template>

<style scoped>
.green {
  position: relative;
  max-width:100%;
  height: 300px;
  border-radius: 0 0 30px 30px;
  background: var(--Linear, linear-gradient(89deg, #BEF440 1.57%, #6DEF9E 99.46%));
  overflow-x: hidden;
  text-align: center;
}
.result_green_img{
  position: absolute;
  bottom: 0;
  left: 25%;
  display: block;
}
.result_green_img__mini{
  display: none;
}
.result{
  display: flex;
  flex-direction: row;
  align-items:center;
  justify-content: center;
  margin-top: 36px !important;

  color: #283128;
  text-align: center;
  font-size: 35px;
  font-weight: 700;
  line-height: 35px;
  gap: 16px;
}
.result_percent{
  max-width: 120px;
  border-radius: 15px;
  background: var(--Linear, linear-gradient(89deg, #BEF440 1.57%, #6DEF9E 99.46%));

  color: #FFF;
  font-size: 35px;
  font-style: normal;
  font-weight: 700;
  line-height: 35px;
  text-align: center;
  padding: 8px 8px;
}
.description{
  margin-top: 36px !important;
}
.recommendations{
  margin-top: 36px !important;
  padding: 24px 102px !important;
  border-radius: 10px;
  background: #F9F9F9;
  display: flex;
  flex-direction: row;
}
.desk_base{
  color: #283128;
  font-size: 24px;
  font-style: normal;
  font-weight: 400;
  line-height: 30px;
}
.container_left{
  width: 580px;
  display: flex;
  flex-direction: column;
  justify-content: left;
  gap: 16px;
}
.desk_h3{
  color: #283128;
  font-size: 35px;
  font-style: normal;
  font-weight: 500;
  line-height: 35px;
}
.hrefs{
  display: flex;
  flex-direction: column;
  justify-content: left;
  gap: 8px;
}
.hrefs_item{
  display: flex;
  flex-direction: row;
  align-items:center;
  gap: 8px;
}
.hrefs_item img{
  width: 14px;
  height: 14px;
  display: block;
}
.container_right img{
  margin-left: 150px;
  width:247px;
}
.next{
  width:300px;
  height: 50px;
  border-radius: 15px;
  margin-top: 24px !important;
  border: 4px solid rgba(158, 192, 157, 0.35);
  background: #FFF;

  color: #283128;
  font-size: 20px;
  font-style: normal;
  font-weight: 500;
  line-height: 30px; /* 111.111% */
}
.next:hover{
  background: rgba(158, 192, 157, 0.6);
}

@media (max-width: 1250px) {
  .result_green_img{
    left: 15%;
  }
  .result{
    margin-top: 24px !important;
  }
  .description{
    margin-top: 24px !important;
  }
  .recommendations{
    margin-top: 24px !important;
  }
}

@media (max-width: 992px) {
  .result_green_img{
    left: 5%;
  }
  .desk_h3{
    color: #283128;
    font-size: 30px;
    font-style: normal;
    font-weight: 500;
    line-height: 30px;
  }
  .container_left{
    gap: 12px;
  }
  .container_right img{
    margin-top: 24px;
    margin-left: 80px;
    width:180px;
  }
  .next{
    margin-top: 16px !important;
  }
}
@media (max-width: 768px) {
  .result{
    font-size: 25px;
    font-style: normal;
    font-weight: 700;
    line-height: 25px;
  }
  .result_percent{
    max-width: 90px;
    border-radius: 10px;
    font-size: 25px;
    line-height: 25px;
  }
  .recommendations{
    flex-direction: column;
    margin-top: 24px !important;
    padding: 16px 48px !important;
  }
  .result_green_img{
    display: none;
  }
  .container_left{
    width:400px;
  }
  .result_green_img__mini{
    position: absolute;
    bottom: 0;
    left: 30%;
    display: block;
  }
  .container_right img{
    margin-top: 24px;
    margin-left: 30%;
    width:150px;
  }
  .desk_base{
    font-size: 18px;
    line-height: 18px;
  }
  .desk_h3{
    font-size: 30px;
    line-height: 30px;
    width: 400px;
  }
}
@media (max-width: 576px) {
  .green{
    height: 194px;
  }
  .container{
    width: 440px !important;
  }
  .result_green_img__mini{
    width: 180px;
    left: 30%;
  }
  .result{
    margin-top: 24px !important;
    font-size: 20px;
    line-height: 20px;
    display: flex;
    flex-direction: row;
  }
  .result_percent{
    max-width: 60px;
    border-radius: 10px;
    font-size: 17px;
    line-height: 17px;
  }
  .desk_h3{
    font-size: 16px;
    font-style: normal;
    font-weight: 500;
    line-height: 20px;
  }
  .desk_base{
    font-size: 14px;
    font-style: normal;
    font-weight: 400;
    line-height: 18px;
  }
  .description{
    margin-top: 24px !important;
  }
  .recommendations{
    margin-top: 24px !important;
  }
  .container_left{
    gap: 8px;
  }
  .next{
    width:300px;
  }
}
@media (max-width: 462px) {
  .green{
    height: 194px;
  }
  .container{
    width: 330px !important;
  }
  .result_green_img__mini{
    width: 180px;
    left: 30%;
  }
  .result{
    margin-top: 24px !important;
    font-size: 14px;
    line-height: 17px;
    display: flex;
    flex-direction: row;
  }
  .desk_h3{
    line-height: 16px;
    width: 300px;
  }
  .desk_base{
    line-height: 14px;
    width: 300px;
  }
  .description{
    margin-top: 24px !important;
  }
  .recommendations{
    margin-top: 24px !important;
    padding: 16px 15px !important;
  }
  .container_left{
    width: 300px;
    gap: 8px;
  }
  .next{
    width:300px;
  }

}
</style>