<template>
 <div class="container-fluid">
  <div class="row">
    <div class="col-lg-6 col-md-12 text">
      <h1 class="main-text">MobiMech Services</h1>
      <p class="sub-text">Browse and select a service from the range of mobile diagnostic, repair and maintenance services we offer.</p>
    </div>
    <div class="col-lg-6 col-md-12">
        <img class="car3" src="https://i.ibb.co/D8jSdwk/gtr.png " alt="car3">
    </div>
  </div>
</div>

    <div class="container" v-if="service">
 
      <div class="row">
        <div class="col">
          <h1>Services</h1>
          <hr class="w-25" style="height: 4px;">
        </div>
      </div>
      <div class="row">
        <div class="col-4">
          <select
            v-model="selected"
            class="form-select my-4"
            aria-label="Default select example"
          >
            <option selected value="">Display All</option>
            <option value="mask">Brakes</option>
            <option value="wetsuits">Ignition</option>
            <option value="camera">Fluids</option>
          </select>
        </div>
        <div class="col-4">
          <form class="d-flex my-4">
            <input
              class="form-control me-2"
              type="text"
              v-model="search"
              placeholder="Search"
              aria-label="Search"
            />
          </form>
        </div>
        <div class="col-4"></div>
      </div>
      <div class="row">
        <div
          class="col-lg-4 col-md-6 w-100 my-3"
          v-for="services of filterServices"
          :key="services._id"
        >
          <div class="card py-4 px-lg-5 h-100">
            <div class="card-body d-flex flex-column">

              <h2 class="card-title text-start">{{ services.title }}</h2>
              <hr class="w-50">
              <div class="pricing">
                <ul class="list-unstyled">
                  <li class="mb-3">
                    <span class="small">{{ services.description }}</span>
                  </li>
                </ul>
                <hr class="my-3 w-25">
              </div>
              <div class="text-start mb-4">
                <span class="fw-bold fs-2">R{{ services.price }}</span>
              </div>
              <div class="text-start">
                <button
                  type="button"
                  class="btn btn-primary rounded-pill"
                  @click="addToCart(services._id)"
                >
                  Add to cart
                </button>
              </div>
            </div>
          </div>
        </div>
      </div>
    </div>
   
    <div
      v-if="isModalVisible"
      class="modal fade"
      id="exampleModal"
      tabindex="-1"
      aria-labelledby="exampleModalLabel"
      aria-hidden="true"
    >
      <div class="modal-dialog">
        <div class="modal-content">
          <div class="modal-header">
            <button
              type="button"
              class="btn-close"
              data-bs-dismiss="modal"
              aria-label="Close"
            ></button>
          </div>
          <div class="modal-footer">
            <button
              type="button"
              class="btn btn-secondary"
              data-bs-dismiss="modal"
            >
              Close
            </button>
            

            <button
              class="btn btn-secondary"
              data-bs-dismiss="modal"
              @click="clearCart"
            >
              Clear Cart
            </button>
          </div>
        </div>
      </div>
    </div>

</template>

<script>

export default {
  components: {
  },
  data() {
    return {
      service: null,
      search: "",
      isModalVisible: false,
  
      selected: "",
    };
  },
  methods: {
    checkout(){
      
    },
    clearCart() {
      fetch("http://localhost:6644/cart/", {
        method: "DELETE",
        headers: {
          "Content-type": "application/json; charset=UTF-8",
          Authorization: `Bearer ${localStorage.getItem("jwt")}`,
        },
      })
        .then((response) => response.json())
        .then((json) => {
          location.reload();
        })
        .catch((err) => {
          alert(err);
        });
    },
    addToCart(id) {
      if (!localStorage.getItem("jwt")) {
        alert("User not logged in");
        return this.$router.push({ name: "Services" });
      } else {
        let cart = 1;
        fetch(`http://localhost:6644/cart/${id}/`, {
          method: "POST",
          body: JSON.stringify({
            quantity: cart,
          }),
          headers: {
            "Content-type": "application/json; charset=UTF-8",
            Authorization: `Bearer ${localStorage.getItem("jwt")}`,
          },
        })
          .then((response) => response.json())
          .then((json) => {
            alert("Added to Cart");
            location.reload();
          })
          .catch((err) => {
            alert(err);
          });
      }
    },
   
  },
  mounted() {
    fetch("http://localhost:6644/services", {
      method: "GET",
      headers: {
        "Content-type": "application/json; charset=UTF-8",
      },
    })
      .then((response) => response.json())
      .then((json) => {
        this.service = json;
      })
      .catch((err) => {
        alert(err);
        console.log(err);
      });
  },
  computed: {
    filterServices: function () {
      let filtered = this.service
      if (this.selected == '') {
          filtered = filtered.filter((service) => {
           return service.category.match(this.selected) ;
          
        });
        if(this.search){
          filtered = filtered.filter((service) =>{
            return service.title.match(this.search)
          })
        }
        return filtered
      }
      if (this.selected) {
        filtered = filtered.filter((service) => {
           return service.category.match(this.selected) ;
          
        });
        if(this.search){
          filtered = filtered.filter((service) =>{
            return service.title.match(this.search)
          })
        }
        return filtered
        
      }
  
      
    },
  },
};
</script>

<style lang="scss" scoped>
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
    margin-bottom: 50px;
  height: 50vh;
  background-color: $secondaryBg;
//   background-image: url(https://i.ibb.co/vh9BXFW/aboutbg.png);
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

    .text    {
    //      
      left: 50px;
      top: 250px;
      color: $tertiaryText;
  }
.main-text{
    margin-top: 120px !important;
}
  .sub-text {
      font-size: 1.2rem;
      width: 75%;
  }
}
.container {

    margin-bottom: 50px;

    .card {
        box-shadow: rgba(255, 255, 255, 0.1) 0px 1px 1px 0px inset, rgba(50, 50, 93, 0.25) 0px 50px 100px -20px, rgba(0, 0, 0, 0.3) 0px 30px 60px -30px;
        border: none;

        span {
            font-size: 1.1em;
            font-weight: normal;
        }

        hr {
            height: 4px;
            color: rgba($color: #00509d, $alpha: 1.0)
        }
    }

    button{
                padding: 10px;
                border: 2px solid rgb(0, 63, 136);
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

    select {
         border-radius: 50px;
                border: none;
                padding: 10px;
                width: 350px;
                 border-radius: 50px;
                border: none;
                padding: 15px;
                width: 350px;
                box-shadow: rgba(0, 0, 0, 0.07) 0px 1px 2px, rgba(0, 0, 0, 0.07) 0px 2px 4px, rgba(0, 0, 0, 0.07) 0px 4px 8px, rgba(0, 0, 0, 0.07) 0px 8px 16px, rgba(0, 0, 0, 0.07) 0px 16px 32px, rgba(0, 0, 0, 0.07) 0px 32px 64px;
    }

    form {
        
        input {
             border-radius: 50px;
                border: none;
                padding: 10px;
                width: 350px;
                 border-radius: 50px;
                border: none;
                padding: 15px;
                width: 350px;
                box-shadow: rgba(0, 0, 0, 0.07) 0px 1px 2px, rgba(0, 0, 0, 0.07) 0px 2px 4px, rgba(0, 0, 0, 0.07) 0px 4px 8px, rgba(0, 0, 0, 0.07) 0px 8px 16px, rgba(0, 0, 0, 0.07) 0px 16px 32px, rgba(0, 0, 0, 0.07) 0px 32px 64px;
        }
    }

    .col {
        
        hr {
            color: rgba($color: #00509d, $alpha: 1.0);
    }
}
        }

    .car3 {
  margin-top: 50px !important;
  float: right;
  height: 250[x];
  width: 650px;
  object-fit: cover;


  @media (max-width: 800px) {
    display: none;
  }
}
</style>