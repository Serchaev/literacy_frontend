<script>
export default {

}
</script>

<template>
<section class="main">
  <div class="container">
    <div class="row">
      <div class="main__title col-7">Узнайте уровень</div>
      <div class="main__stars col-2">
        <img src="@/assets/starts.png" alt="">
      </div>
      <div class="main__title col-3">своей</div>
      <div class="main__title main__title_green offset-1 col-5 mt-lg-3 mt-1 mb-lg-5">финансовой</div>
      <div class="main__title col-5">грамотности</div>
    </div>
    <div class="main__btn col-12 d-flex justify-content-center align-items-center mt-5">
      <button class="main__button col-lg-4 col-11" @click="this.$router.push('/test')">Играть</button>
    </div>
  </div>
</section>
</template>

<style scoped>
.main{
  padding: 36px 0;
}
.main__title{
  color: #31290E;
  font-size: 75px;
  font-weight: 300;
  line-height: 100px;
  text-align: center;
}
.main__title_green{
  border-radius: 40px;
  background: linear-gradient(89deg, #BEF440 1.57%, #6DEF9E 99.46%);
  transform: rotate(-6.057deg);
  color: #FFF;
  font-weight: 400;
}
.main__stars img{
  width: 100%;
}
.main__button{
  text-align: center;
  border: none;
  border-radius: 25px;
  background: #148F2B;
  box-shadow: 0 4px 19px 0 rgba(158, 192, 157, 0.25), 6px 4px 24px 0 rgba(190, 244, 64, 0.70) inset;
  padding: 8px 0;
  color: #FFF;
  font-size: 40px;
  font-weight: 500;
  line-height: 55px;
}
@media (max-width: 1400px) {
  .main__title{
    font-size: 68px;
    line-height: 92px;
  }
}
@media (max-width: 1200px) {
  .main__title{
    font-size: 50px;
    line-height: 80px;
  }
}
@media (max-width: 992px) {
  .main__title{
    font-size: 36px;
    line-height: 70px;
  }
  .main__button{
    border-radius: 15px;
    font-size: 20px;
    line-height: 40px;
  }
}
@media (max-width: 768px) {
  .main__title{
    font-size: 26px;
    line-height: 50px;
  }
}
@media (max-width: 576px) {
  .main__title{
    font-size: 20px;
    line-height: 40px;
  }
}
@media (max-width: 320px) {
  .main__title{
    font-size: 16px;
    line-height: 30px;
  }
}
</style>