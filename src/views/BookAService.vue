<template>
  <div class="container-fluid">
  <div class="row">
    <div class="col-lg-6 col-md-12">
      <h1 class="main-text">Book a Service</h1>
      <p class="sub-text">Let’s get your car back in tip-top shape! A few simple questions will get you a free quote.</p>
    </div>
  </div>
</div>
<BASInfo/>
</template>

<script>
import BASInfo from '@/components/BASInfo.vue'
export default {
name: "BookAService",
components: {
    BASInfo
}
}
</script>

<style scoped lang="scss">
$primaryText : #021a49;
$secondaryText : #171D24;
$tertiaryText : #fff;
//color theme
$primaryBg : #00509d;
$secondaryBg : #003f88;
$tertiaryBg : #00296b;
//fonts
@import url('https://fonts.googleapis.com/css2?family=Poppins:ital,wght@0,300;0,400;0,900;1,200;1,300&family=Rubik:ital,wght@0,300;0,400;0,500;0,600;0,700;1,300;1,400&display=swap');
$primaryFont: 'Poppins', sans-serif;
$secondaryFont: 'Rubik', sans-serif;
//Styling
.container-fluid{
  height: 50vh;
  background-color: $secondaryBg;
  background-image: url(https://i.ibb.co/vh9BXFW/aboutbg.png);
  background-repeat: no-repeat;
  background-attachment: fixed;
  background-position: right;
  background-position-y: 100px !important;
  background-size: 30% 50%;
  z-index: -1000 !important;

  @media (max-width:1000px) {
    background-position: right;
    height: 100vh;
  }

  @media (max-width: 768px) {
    background-size: cover;
  }

  .col-md-12 {
      position: absolute;
      left: 50px;
      top: 250px;
      color: $tertiaryText;
  }

  .sub-text {
      font-size: 1.2rem;
      width: 75%;
  }

}

</style>