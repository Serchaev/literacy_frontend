<script>
export default {

}
</script>

<template>
  <section class="header">
    <div class="container">
      <div class="row">
        <div class="header__brand col-lg-3 col-12 d-flex justify-content-center align-items-center">
          <img src="@/assets/brand.png" alt="">
        </div>
        <div class="header__menu offset-xxl-5 col-xxl-4 offset-lg-4 col-lg-5 d-none d-lg-flex justify-content-between align-items-center">
          <div><a class="header__link" href="#about">Об игре</a></div>
          <div>
            <img src="@/assets/menu4.png" alt="">
          </div>
          <div>
            <img src="@/assets/menu1.png" alt="">
          </div>
          <div>
<!--            <img src="@/assets/menu3.png" alt="">-->
            <img src="@/assets/menu2.png" alt="">
          </div>
          <div>
            <button class="header__btn" @click="this.$router.push('/test')">Играть</button>
          </div>
        </div>
      </div>
    </div>
  </section>
</template>

<style scoped>
.header{
  padding: 20px 0;
}
.header__btn{
  border: none;
  border-radius: 10px;
  background: #148F2B;
  box-shadow: 0 4px 19px 0 rgba(158, 192, 157, 0.25), 6px 4px 24px 0px rgba(190, 244, 64, 0.70) inset;
  color: #FFF;
  font-size: 20px;
  font-weight: 500;
  padding: 7px 35px;
}
.header__link{
  color: black;
  text-decoration: none;
}
</style>