<template>
<div class="container-fluid">
  <div class="row">
    <div class="col-lg-6 col-md-12">
      <h1 class="main-text">Our goal is to make car care affordable, convenient, and transparent.</h1>
      <p class="sub-text">We’re here to give you back the confidence in your car repair and maintenance service needs</p>
    </div>
    <div class="col-lg-6 col-md-12"><img class="mech-work" src="https://i.ibb.co/VS3qdDv/mech-at-work.jpg" alt="mech-at-work"></div>
  </div>
</div>
  <MoreInfo />
</template>

<script>
import MoreInfo from '../components/MoreInfo.vue'

  export default {
    name: 'About',
components: {
    MoreInfo
}

  }
</script>

<style lang="scss" scoped>
  //text color
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
  height: 86.5vh;
  background-color: $secondaryBg;
  background-image: url(https://i.ibb.co/vh9BXFW/aboutbg.png);
  background-repeat: no-repeat;
  background-attachment: fixed;
  background-position: right;
  background-position-y: 128px !important;
  background-size: 60% 80%;
  z-index: -1000 !important;

  @media (max-width:1000px) {
    background-position: right;
    height: 100vh;
  }

  @media (max-width: 768px) {
    background-size: cover;
  }
  .main-text{
    font-weight: 600 !important;
    font-size: 50px;
    bottom: 0 !important;
    margin-left: 10px;
    margin-top: 30% !important;
     color: $tertiaryText;
  }
  .sub-text{
    bottom: 0 !important;
    margin-left: 10px;
    margin-top: 1% !important;
     color: $tertiaryText;
     
  }
 

}
 .mech-work{
   margin-top: 30%;
    width: 450px !important;
    height: 300px !important;
    border-radius: 20px;
    margin-left: 100px !important;
    object-fit: cover;
  }
</style>