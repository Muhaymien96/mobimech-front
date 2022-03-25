<template>
  <div class="Info">
      <form action="POST" class="booking"></form>
      <div class="row">
          <div class="col-sm-8">
    <div class="accordion accordion-flush w-75 mx-auto" id="accordionFlushExample">
  <div class="accordion-item">
    <h2 class="accordion-header" id="flush-headingOne">
      <button class="accordion-button collapsed p-4 " style="font-weight: 700; color: rgba(0, 0, 0, .6)" type="button" data-bs-toggle="collapse" data-bs-target="#flush-collapseOne" aria-expanded="false" aria-controls="flush-collapseOne">
        Enter your Address
      </button>
    </h2>
    <div id="flush-collapseOne" class="accordion-collapse collapse" aria-labelledby="flush-headingOne" data-bs-parent="#accordionFlushExample">
      <div class="accordion-body">
          <input type="text" placeholder="Enter Your Address" id="autocomplete" v-model="address" required>
          <button class="mx-4" @click="saveAddress">Confirm Location</button></div>
    </div>
  </div>
  <div class="accordion-item">
    <h2 class="accordion-header" id="flush-headingTwo">
      <button class="accordion-button collapsed p-4" style="font-weight: 700; color: rgba(0, 0, 0, .6)" type="button" data-bs-toggle="collapse" data-bs-target="#flush-collapseTwo" aria-expanded="false" aria-controls="flush-collapseTwo">
        Select your Vehicle
      </button>
    </h2>
    <div id="flush-collapseTwo" class="accordion-collapse collapse" aria-labelledby="flush-headingTwo" data-bs-parent="#accordionFlushExample">
      <div class="accordion-body">Placeholder content for this accordion, which is intended to demonstrate the <code>.accordion-flush</code> class. This is the second item's accordion body. Let's imagine this being filled with some actual content.</div>
    </div>
  </div>
  <div class="accordion-item">
    <h2 class="accordion-header" id="flush-headingThree">
      <button class="accordion-button collapsed p-4" style="font-weight: 700; color: rgba(0, 0, 0, .6)" type="button" data-bs-toggle="collapse" data-bs-target="#flush-collapseThree" aria-expanded="false" aria-controls="flush-collapseThree">
        Select your Service
      </button>
    </h2>
    <div id="flush-collapseThree" class="accordion-collapse collapse" aria-labelledby="flush-headingThree" data-bs-parent="#accordionFlushExample">
      <div class="accordion-body">Placeholder content for this accordion, which is intended to demonstrate the <code>.accordion-flush</code> class. This is the third item's accordion body. Nothing more exciting happening here in terms of content, but just filling up the space to make it look, at least at first glance, a bit more representative of how this would look in a real-world application.</div>
    </div>
  </div>
    <div class="accordion-item">
    <h2 class="accordion-header" id="flush-headingFour">
      <button class="accordion-button collapsed p-4" style="font-weight: 700; color: rgba(0, 0, 0, .6)" type="button" data-bs-toggle="collapse" data-bs-target="#flush-collapseFour" aria-expanded="false" aria-controls="flush-collapseFour">
        select your Date/Time
      </button>
    </h2>
    <div id="flush-collapseFour" class="accordion-collapse collapse" aria-labelledby="flush-headingFour" data-bs-parent="#accordionFlushExample">
      <div class="accordion-body">Placeholder content for this accordion, which is intended to demonstrate the <code>.accordion-flush</code> class. This is the third item's accordion body. Nothing more exciting happening here in terms of content, but just filling up the space to make it look, at least at first glance, a bit more representative of how this would look in a real-world application.</div>
    </div>
  </div>
</div>
</div>
          <div class="col-sm-4">
              <div id="summary">
              <h5>Total Cost</h5>
              <h2 class="display-5" style="font-weight: bold;">R<span>INC.VAT</span></h2>
              <br><br><br>
              <div class="row">
                  <div class="col-sm-6">
              <ul>
                  <li>Labour</li>
                  <li class="mt-2">Parts</li>
                  <li class="mt-2">Travel Fee</li>
                  <li class="mt-2">Service Fee</li>
              </ul>

                  </div>
                  <div class="col-sm-6 fee">
                      <ul class="text-end">
                          <li>R</li>
                          <li class="mt-2">R</li>
                          <li class="mt-2">R</li>
                          <li class="mt-2">R</li>
                      </ul>
                  </div>
                  <hr class="my-4">
                  <h6 style="font-weight: bold;">SUMMARY</h6>
              </div>
              </div>
          </div>
      </div>
  </div>
</template>

<script>
export default {
components : {

},
data(){
    return {
        address: ""
    };
},
mounted(){
    new google.maps.places.Autocomplete(
        document.getElementById("autocomplete"),
         {
           bounds: new google.maps.LatLngBounds(
               new google.maps.LatLng(-30.559482, 22.937506)
           )
        }

    )
},
saveAddress() {
      fetch("http://localhost:6644/bookings", {
        method: "POST",
        body: JSON.stringify({
          address: this.address,
        }),
        headers: {
          "Content-type": "application/json; charset=UTF-8",
        },
      })
        .then((response) => response.json())
        .then((json) => {
          alert("Address Confirmed");
          localStorage.setItem("jwt", json.jwt);
        })
        .catch((err) => {
          alert(err);
        });
    },

}
</script>

<style lang="scss" scoped>
.Info {
     background-image: url(https://i.ibb.co/vh9BXFW/aboutbg.png);
  background-repeat: no-repeat;
  background-attachment: fixed;
  background-position: left;
  background-position-y: 100px !important;
  background-size: 60% 90%;
  z-index: -1000 !important;
  margin: 75px auto;

    .row {
        width: 100%;
    }

    .col-sm-4 {
        background: rgb(0,98,157);
background: linear-gradient(0deg, rgba(0,98,157,1) 0%, rgba(0,63,136,1) 58%);
        color: #fff;
        border-radius: 40px;
        box-shadow: rgba(50, 50, 93, 0.25) 0px 13px 27px -5px, rgba(0, 0, 0, 0.3) 0px 8px 16px -8px;
        margin-inline: auto;

        #summary {
            margin: 30px;

            li {
                list-style: none;
                margin-left: -25px;
            }
            
        }

        h2{

            span {
                font-size: .3em;
            }
        }
    }

    .accordion {
        box-shadow: rgba(50, 50, 93, 0.25) 0px 13px 27px -5px, rgba(0, 0, 0, 0.3) 0px 8px 16px -8px;
        border-radius: 10px !important;
     .accordion .accordion-flush{
         border-radius: 10px !important;
     }

        .accordion-body {

            padding: 40px 40px;


            input{
                opacity: .5;
                border-radius: 50px;
                border: none;
                padding: 15px;
                width: 350px;
                box-shadow: rgba(0, 0, 0, 0.07) 0px 1px 2px, rgba(0, 0, 0, 0.07) 0px 2px 4px, rgba(0, 0, 0, 0.07) 0px 4px 8px, rgba(0, 0, 0, 0.07) 0px 8px 16px, rgba(0, 0, 0, 0.07) 0px 16px 32px, rgba(0, 0, 0, 0.07) 0px 32px 64px;
            }

            button{
                padding: 20px;
                border: 2px solid rgb(0, 63, 136);
                border-radius: 40px;
                color: #fff;
                font-weight: 700;
                background: rgb(0,98,157);
                background: linear-gradient(0deg, rgba(0,98,157,1) 0%, rgba(0,63,136,1) 100%);
                transition: .5s ease all;

                &:hover {
                    background: transparent;
                    color: rgb(0, 63, 136);
                    border: 2px solid rgb(0, 63, 136);
                    transition: .5s ease all;
                }
            }
        }

        
    }
}
</style>