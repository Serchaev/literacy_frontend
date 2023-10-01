<script>
export default {

}
</script>

<template>
  <section class="themes mt-5 pt-5 pb-5">
    <div class="container">
      <div class="themes__title offset-xxl-3 col-xxl-6 offset-lg-2 col-lg-8 offset-1 col-10">
        Вас ждут вопросы по темам:
      </div>
      <div class="row">
        <div class="col-12 col-lg-3 mt-4">
          <div class="themes__item themes__item1">
            <span>Личные финансы</span>
            <div class="themes__img">
              <img src="@/assets/themes1.png" alt="">
            </div>
          </div>
        </div>
        <div class="col-12 col-lg-6 mt-4">
          <div class="themes__item themes__item2">
            <span class="">Основы финансовой грамотности в литературных произведениях</span>
            <div class="themes__img">
              <img src="@/assets/themes2.png" alt="">
            </div>
          </div>
        </div>
        <div class="col-12 col-lg-3 mt-4">
          <div class="themes__item themes__item3">
            <span>Страхование</span>
            <div class="themes__img">
              <img src="@/assets/themes3.png" alt="">
            </div>
          </div>
        </div>
      </div>
      <div class="row">
        <div class="col-12 col-lg-6 mt-4">
          <div class="themes__item themes__item4">
            <span>Банки и кредитование</span>
            <div class="themes__img">
              <img src="@/assets/themes4.png" alt="">
            </div>
          </div>
        </div>
        <div class="col-12 col-lg-6 mt-4">
          <div class="themes__item themes__item5">
            <span>Финансовая безопасность</span>
            <div class="themes__img">
              <img src="@/assets/themes5.png" alt="">
            </div>
          </div>
        </div>
      </div>
    </div>
  </section>
</template>

<style scoped>
.themes__title{
  text-align: center;
  color: #283128;
  font-size: 55px;
  font-weight: 500;
  line-height: 55px;
}
.themes__item{
  position: relative;
  padding: 32px 24px;
  height: 350px;
  border-radius: 10px;
}
.themes__item1{
  background: linear-gradient(90deg, #6AEEA2 0%, #93F175 100%);
}
.themes__item2{
  background: linear-gradient(90deg, #94F173 0%, #B7F44E 100%);
}
.themes__item3{
  background: linear-gradient(90deg, #B6F450 0%, #C4F53C 100%);
}
.themes__item4{
  background: var(--Linear, linear-gradient(89deg, #BEF440 1.57%, #6DEF9E 99.46%));
}
.themes__item5{
  background: linear-gradient(270deg, #BEF440 2.32%, #6DEF9E 99.83%);
}
.themes__item span{
  color: #FFF;
  text-shadow: 0 4px 80px rgba(40, 49, 40, 0.30);
  font-size: 35px;
  font-weight: 500;
  text-transform: uppercase;

}
.themes__img{
  position: absolute;
  bottom: 0;
  right: 0;
}
@media (max-width: 1400px) {
  .themes__item span{
    font-size: 28px;
  }
  .themes__item2 .themes__img img{
    width: 150px;
  }
}
@media (max-width: 1200px) {
  .themes__item span{
    font-size: 22px;
  }
}
@media (max-width: 992px) {
  .themes__item{
    height: 250px;
  }
  .themes__item2 .themes__img img{
    width: 120px;
  }
  .themes__title{
    font-size: 42px;
    line-height: 42px;
  }
}
@media (max-width: 576px) {
  .themes__item{
    height: 200px;
  }
  .themes__item span{
    font-size: 20px;
  }
  .themes__img img{
    width: 150px;
  }
  .themes__item2 .themes__img img{
    width: 90px;
  }
  .themes__item4 .themes__img img{
    width: 90px;
  }
  .themes__item5 .themes__img img{
    width: 90px;
  }
  .themes__title{
    font-size: 28px;
    line-height: 28px;
  }
}
@media (max-width: 320px) {
  .main__title{
    font-size: 16px;
    line-height: 30px;
  }
}
</style>