<template>
  <div class="contain">
    <div class="row">
      <div class="col-lg-6 col-md-12"><img class="drive" src="https://i.ibb.co/JjzPz8B/about1.webp" alt="drive" /></div>
      <div class="col-lg-6 col-md-12">
        <div class="card1">
          <h2 class="card-head">OUR DRIVE</h2>
          <br />
          <p class="info-text">
            MobiMech is not just another car repair and maintenance company. We
            leverage technology to find better ways to provide convenient,
            transparent and quality car repair and maintenance services;
            wherever our customers are and whenever they need us
          </p>
          <button type="button" class="btn-outline-primary rounded-pill">
            Register With MobiMech
          </button>
        </div>
      </div>
    </div>
    <div class="row">
      <div class="col-lg-6 col-md-12">
        <div class="card2">
          <h2 class="head">OUR COMMITMENT</h2>
          <br />
          <p class="info-text">
            It is essential to us that you can be confident in the mechanic's
            quality servicing your vehicle, the price's fairness or where in the
            process your car is. <br /><br />

            Mechanics put in hard and honest work repairing vehicles. Looking to
            grow their careers and businesses, we manage the end-to-end customer
            relationship, helping customers find them and allowing them to focus
            on what they love.
          </p>
          <button type="button" class="btn-outline-primary rounded-pill">
            Register With MobiMech
          </button>
        </div>
      </div>
      <div class="col-lg-6 col-md-12"><img class="drive2" src="https://i.ibb.co/hFcYfB2/drive2.webp" alt="drive2"></div>
    </div>
  </div>
</template>

<script>
export default {};
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
$componentBg: white;
//fonts
$primaryFont: "Poppins", sans-serif;
$secondaryFont: "Rubik", sans-serif;
//styling
// https://i.ibb.co/4tj7rbp/graphic-left-home.png.png
.contain {
  height: max-content;
  background-color: $componentBg;
  background-image: url(https://i.ibb.co/FXPwx07/homebg.png.png);
  background-repeat: no-repeat;
  background-attachment: fixed;
  background-position: right;
  background-size: 40% 60%;
  z-index: -1000 !important;
  background-position-y: 128px !important;
  overflow-x: hidden;


.drive{
  margin-top: 40px;
  margin-left: 60px;
  margin-right: auto;
    height: 370px;
    width: 540px;
    border-radius: 12px;
    object-fit: cover;
}
.drive2{
  margin-top: 40px;
  margin-left: 60px;
  margin-right: auto;
    height: 435px;
    width: 540px;
    border-radius: 12px;
    object-fit: cover;
}
  .card1 {
    background-color: $componentBg;
    box-shadow: 0px 0px 20px 0px rgb(0 0 0 / 13%);
    transition: background 0.3s, border 0.3s border-radius 0.3s, box-shadow 0.3s;
    padding: 8% 8% 8% 8%;
    border-radius: 12px;
    margin-top: 40px;
    margin-left: auto;
    margin-right: auto;
    width: 540px;
    .card-head {
      border-bottom: 3px solid $primaryBg;
      width: 170px !important;
    }
    .info-text {
      opacity: 0.8;
    }
  }
  .card2 {
    background-color: $componentBg;
    box-shadow: 0px 0px 20px 0px rgb(0 0 0 / 13%);
    transition: background 0.3s, border 0.3s border-radius 0.3s, box-shadow 0.3s;
    padding: 8% 8% 8% 8%;
    border-radius: 12px;
    margin-top: 40px;
    margin-left: auto;
    margin-right: auto;
    width: 540px;
    margin-bottom: 30px;

    .head {
      border-bottom: 3px solid $primaryBg;
      width: 295px !important;
    }
  }

  @media (max-width: 1000px) {
    background-position: right;
    height: 100vh;
  }

  @media (max-width: 768px) {
    background-size: cover;
  }
}
.btn-outline-primary {
  background-color: $secondaryBg;
  color: $componentBg;
  border-radius: 10px;
  width: 440px;
  height: 50px;
  transition: 0.4s ease all;

  &:hover {
    background-color: $tertiaryText;
    transition: 0.4s ease all;
    color: $primaryBg;
  }
}
</style>
