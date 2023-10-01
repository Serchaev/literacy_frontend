<script setup>

</script>

<template>
  <section class="organizer mt-5">
    <div class="container">
      <h2 class="organizer_h2 mb-4">Организатор</h2>
      <div class="row organizer_content mt-4">
        <div class="greeting_text col-lg-8 col-12 d-flex flex-column mt-md-4 mt-sm-3 ps-md-5 ps-sm-4">
          <h3 class="mt-4">РЦФГ «Финикум»</h3>
          <p class="mt-md-3 mt-sm-2">РЦФГ «Финикум» является структурным подразделением РГЭУ (РИНХ). Главное направление деятельности — повышение уровня финансовой культуры жителей региона.</p>
        </div>
        <div class="col-lg-3 col-12 offset-lg-1 d-flex justify-content-lg-end align-items-lg-end justify-content-center align-items-center">
          <img src="@/assets/organizer_img.png" class="img-fluid " alt="">
        </div>
      </div>
    </div>
  </section>

  <section class="organizer mt-5 pb-5">
    <div class="container">
      <h2 class="organizer_h2 mb-4">Соорганизаторы</h2>
      <div class="row organizer_content mt-4">
        <div class="greeting_text col-lg-8 col-12 d-flex flex-column mt-md-4 mt-sm-3 ps-md-5 ps-sm-4">
          <h3 class="mt-4">Ассоциация Развития <br/> Финансовой Грамотности</h3>
          <p class="mt-md-3 mt-sm-2">Деятельность АРФГ направлена на финансовую и организационную поддержку частных и общественных инициатив в области финансового просвещения населения России, масштабирование лучших практик в сфере финансовой грамотности, а также поддержку, координацию и обучение волонтеров финансового просвещения.</p>
        </div>
        <div class="col-lg-3 col-12 offset-lg-1 d-flex justify-content-lg-end align-items-lg-end justify-content-center align-items-center">
          <img src="@/assets/organizer_img_arfg.png" class="img-fluid " alt="">
        </div>
      </div>
      <div class="row organizer_content mt-4">
        <div class="order-2 order-lg-1 col-lg-3 col-12 d-flex justify-content-lg-end align-items-lg-end justify-content-center align-items-center">
          <img src="@/assets/organizer_img_mfro.png" class="img-fluid " alt="">
        </div>
        <div class="greeting_text order-1 order-lg-2 col-lg-8 col-12 offset-lg-1 d-flex flex-column mt-md-4 mt-sm-3 pe-md-5 ps-sm-4">
          <h3 class="mt-4 text-start text-lg-end">Министерство финансов <br/> Ростовской области</h3>
          <p class="mt-md-3 mt-sm-2 text-start text-lg-end">Деятельность министерства финансов РО направлена на обеспечение финансовой стабильности в регионе через эффективное и бережное управление государственными финансами, развитие, обеспечение стабильности и повышение надежности финансовой системы, а также выполнение функций нормативно-правового регулирования в финансовой, бюджетной и налоговой сферах.</p>
        </div>
      </div>
      <div class="row organizer_content mt-4">
        <div class="greeting_text col-lg-8 col-12 d-flex flex-column mt-md-4 mt-sm-3 ps-md-5 ps-sm-4">
          <h3 class="mt-4">Ростовский государственный <br/> экономический университет (РИНХ)</h3>
          <p class="mt-md-3 mt-sm-2">РГЭУ (РИНХ) - крупный многопрофильный образовательный и учебно-методический центр юга России, использующий новейшие методики и технологии обучения.</p>
        </div>
        <div class="col-lg-3 col-12 offset-lg-1 d-flex justify-content-lg-end align-items-lg-end justify-content-center align-items-center">
          <img src="@/assets/organizer_img_rsue.png" class="img-fluid " alt="">
        </div>
      </div>
    </div>
  </section>
</template>

<style scoped>
.organizer_content{
  border-radius: 10px;
  border: none;
  background: #F9F9F9;
}
.greeting_text h3, .benefit_text h3{
  color: #283128;
  font-size: 35px;
  font-weight: 500;
  line-height: 35px; /* 100% */
}
.greeting_text p, .list_items p{
  color: #283128;
  font-size: 24px;
  font-weight: 400;
  line-height: 24px; /* 125% */
}
.organizer_h2{
  color: #283128;
  text-align: center;
  font-size: 55px;
  font-weight: 500;
  line-height: 55px;
}
@media (max-width: 992px){
  .greeting_text h3, .benefit_text h3{
    font-size: 25px;
    line-height: 25px; /* 122.222% */
  }
  .greeting_text p, .list_items p{
    font-size: 20px;
    line-height: 20px; /* 128.571% */
  }
  .img-fluid{
    width: 237px;
  }

  .organizer_h2{
    font-size: 35px;
    line-height: 35px;
  }
}

@media (max-width: 576px){
  .greeting_text h3, .benefit_text h3{
    font-size: 18px;
    line-height: 22px; /* 122.222% */
  }
  .greeting_text p, .list_items p{
    font-size: 14px;
    line-height: 18px; /* 128.571% */
  }
  .img-fluid{
    width: 180px;
  }
  .organizer_h2{
    font-size: 22px;
    line-height: 22px;
  }
  .organizer{
    padding: 0 12px;
  }
}
</style>