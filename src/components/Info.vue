<template>
  <div class="About">
    <div class="row">
      <div class="col-sm-6">
        <i class="fa-solid fa-calendar-days"></i>
        <h4>WE COME TO YOU</h4>
        <p>Book a repair or maintenance service online 24/7. Our mobile mechanics will come to your home or office.</p>
        <br>
        <i class="fa-solid fa-heart"></i>
        <h4>DIAGNOSTICS & INSPECTIONS</h4>
        <p>If you are unsure about what’s wrong with your car but you just know you have a problem select from our list
          of diagnostic services.</p>
        <br>
        <i class="fa-solid fa-circle-check"></i>
        <h4>VERIFIED MECHANICS</h4>
        <p>We work with only the best mobile mechanics who are verified to have the individual skills required to give
          your car the best care possible.</p>
      </div>
      <div class="col-sm-6">
        <i class="fa-solid fa-calculator"></i>
        <h4>BEST PRICES</h4>
        <p>Because we don’t have all those unnecessary overheads we are able to offer you the best possible prices with
          all the savings passed onto YOU!</p>
        <br>
        <i class="fa-solid fa-wrench"></i>
        <h4>QUALITY PARTS</h4>
        <p>We offer high-quality parts from leading manufacturers of aftermarket/OEM parts.</p>
        <br>
        <i class="fa-solid fa-face-smile"></i>
        <h4>GUARANTEED WORKMANSHIP</h4>
        <p>We only work with highly rated mobile mechanics and all services are backed by our 6-month / 10 000km
          warranty.</p>
      </div>
    </div>
  </div>
</template>

<script>
  export default {
    name: 'About',


  }
</script>

<style lang="scss" scoped>
  $primaryText: #00509d;

  .About {
    margin-top: 100px;

    .row {
      width: 100%;
      margin-inline: auto;

      .col-sm-6 {
        width: 25%;
        margin-inline: auto;

        p {
          font-size: 1.15em;
          margin-inline: auto;
        }

        i {
          color: $primaryText;
          font-size: 3rem;
          float: left;
          margin-left: -80px;
          margin-top: 30px;
        }
      }
    }
  }
</style>