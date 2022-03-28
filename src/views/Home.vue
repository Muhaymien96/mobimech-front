<template>
  <div class="container-fluid">
    <div class="row">
      <div class="col info">
        <div class="text">
          <h2 class="main-text">Mobile mechanics that come to you</h2>
          <p class="sub-text">
            Service at your home or office | Fair and transparent pricing | <br>
            6-month / 10 000km warranty
          </p>
        </div>
        <button type="button" class="btn btn-outline-primary rounded-pill bas"><router-link :to="{name: 'BookAService'}">Book A Service</router-link></button>
      </div>
      <div class="col">
        <img class="car2" src="https://i.ibb.co/5KC3Y7y/car.png" alt="car2" />
      </div>
    </div>
  </div>
    <Info/>
    <HowItWorks/>
</template>

<script>
import Info from '../components/Info.vue'
import HowItWorks from '../components/HowItWorks.vue'
export default {
  name: "Home",
  components: {Info, HowItWorks},
};
</script>
<style lang="scss" scoped>
//text color
$primaryText: #021a49;
$secondaryText: #171d24;
$tertiaryText: #fff;
//color theme
$primaryBg: #00509d;
$secondaryBg: #003f88;
$tertiaryBg: #00296b;
//fonts
$primaryFont: "Poppins", sans-serif;
$secondaryFont: "Rubik", sans-serif;
//styling

.container-fluid {
  height: 88vh;
  background-color: $secondaryBg;
  background-image: url(https://i.ibb.co/FXPwx07/homebg.png);
  background-repeat: no-repeat;
  background-attachment: fixed;
  background-position: left;
  background-size: 60% 80%;
  z-index: -1000 !important;

  @media (max-width:1000px) {
    background-position: right;
    height: 100vh;
  }

  @media (max-width: 768px) {
    background-size: cover;
  }

  .text{
    position: absolute;
    bottom: 40%;
    left: 50px;
  }

.main-text {
  font-weight: 500;
  font-family: $primaryFont;
  color: $tertiaryText;  
}

.sub-text {
  font-family: $primaryFont;
  color: $tertiaryText;
}
.bas{
  font-weight: bold;
background-color: $tertiaryText;  
border-radius: 10px;
width: 170px;
height: 50px;
transition: 0.4s ease all;
position: absolute;
bottom: 30%;
left: 50px;


&:hover{
background-color: $secondaryBg;
transition: 0.4s ease all;
}

}
a:hover{
  color: $tertiaryText;
}

.car2 {
  margin-top: 45px !important;
  height: 500px;
  width: 800px;

  @media (max-width: 1000px) {
    display: none;
  }
}
.info{
  margin-left: 30px !important;
}
}
</style>
