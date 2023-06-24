<template>
  <br /><br /><br /><br />
  <div class="container">
    <div class="row">
      <div class="col-lg-8 col-md-7 col-sm-12">
        <div class="card text-bg-dark">
          <img
            src="https://transvelo.github.io/freshcart/assets/images/slider-image-1.jpeg"
            class="card-img"
            alt="product-img"
          />
          <div class="card-img-overlay text-dark card-one ml-5">
            <h5 class="card-title">
              <p class="m-0 border position-relative" style="padding: 5px">
                Exclusive Offer
                <span
                  class="position-absolute top-0 start-100 translate-middle badge rounded-pill bg-danger"
                >
                  15
                </span>
              </p>
            </h5>
            <h2 class="card-text card-one-text">
              Best Online Deals, <br />
              Free Stuff
            </h2>
            <p class="card-text m-0">Only on this week… Don’t miss</p>
            <p class="card-text">
              <v-btn rounded="lg" color="success">
                Get Best Deal
                <i class="fa-solid fa-arrow-right-long mx-2 mt-1 fa-fade"></i>
              </v-btn>
            </p>
          </div>
        </div>
      </div>

      <div class="col-lg-4 col-md-5 col-sm-12">
        <div class="card text-bg-dark mt-2">
          <img
            src="https://transvelo.github.io/freshcart/assets/images/ad-banner-1.jpeg"
            class="card-img"
            alt="product-img"
          />
          <div class="card-img-overlay text-dark card-two">
            <h3 class="card-title card-two-title">
              10% cashback on <br />
              personal care
            </h3>
            <h5 class="card-text">cashback: $12</h5>
            <h5 class="card-text">
              Code: <strong style="color: #001e2b">CARE12</strong>
            </h5>
            <p class="card-text">
              <v-btn
                rounded="lg"
                class="text-light"
                style="background-color: #001e2b"
              >
                Shop Now
              </v-btn>
            </p>
          </div>
        </div>

        <div class="card text-bg-dark mt-2">
          <img
            src="https://transvelo.github.io/freshcart/assets/images/ad-banner-2.jpeg"
            class="card-img"
            alt="product-img"
          />
          <div class="card-img-overlay text-dark card-two">
            <h3 class="card-title card-two-title">
              Say yes to <br />
              season’s fresh
            </h3>
            <h5 class="card-text">Refresh your day</h5>
            <h6 class="card-text">the fruity way</h6>
            <p class="card-text">
              <v-btn
                rounded="lg"
                class="text-light"
                style="background-color: #001e2b"
              >
                Shop Now
              </v-btn>
            </p>
          </div>
        </div>
      </div>
    </div>
  </div>

  <br /><br />

  <!-- Start  Shop Popular Categories -->
  <div class="my-5 text-start">
    <div class="container">
      <h3>Shop Popular Categories</h3>
      <div class="row my-5">
        <div class="col-lg-3 col-sm-6 col-md-6 mt-5" v-for="i in 12" :key="i">
          <div class="prod">
            <img
              class="img"
              src="https://www8.0zz0.com/2023/05/19/12/288601968.png"
              alt="p-one"
            />
            <p>Rice</p>
          </div>
        </div>
      </div>
    </div>
  </div>
  <!-- End  Shop Popular Categories -->
  <br /><br />
  <!-- Start Products -->
  <CardsComp />
  <!-- End  New Products -->

  <div class="my-5">
    <div class="container">
      <div class="row p-3" style="background: lightgray">
        <div class="col-lg-6 col-sm-12 col-md-12 mt-5">
          <div class="respons">
            <h3>One Stop Grocery Shop</h3>
            <p>
              Shopping for your furry friend? <br />
              Find food, treats, and more in one easy spot.
            </p>
            <v-btn rounded="lg" color="success" class="mb-3">
              Get Discount on share
              <i class="fa-solid fa-arrow-right-long mx-2 mt-1 fa-fade"></i>
            </v-btn>
          </div>
        </div>

        <div class="col-lg-6 col-sm-12 col-md-12 mt-5">
          <img
            src="https://transvelo.github.io/freshcart/assets/images/store-graphics.svg"
            class="img-fluid"
            alt="respon-img"
          />
        </div>
      </div>
    </div>
  </div>
  <br /><br /><br /><br /><br />
</template>

<script>
import CardsComp from "./CardsComp.vue";
export default {
  components: { CardsComp },
};
</script>

<style lang="scss" scoped>
.img {
  width: 150px;
  border-radius: 45%;
  background-image: linear-gradient(
    rgba(249, 243, 243, 0.5),
    rgba(249, 243, 243, 0.5)
  );
  transition: 0.5s ease;
}
.prod,
.respons {
  display: flex;
  align-items: center;
  justify-content: center;
  flex-direction: column;
  gap: 15px;
}

.prod:hover {
  p {
    color: green;
  }
  .img {
    box-shadow: 0 10px 20px 5px;
    transform: scale(1.1);
  }
}

h3 {
  color: #001e2b;
}
.card {
  border-radius: calc(0.375rem - 1px);
}
.card-one,
.card-two {
  display: flex;
  align-items: flex-start;
  justify-content: center;
  flex-direction: column;
  gap: 0.5rem;
}
.btn {
  cursor: auto;
}

//Phone
@media screen and (max-width: 767px) {
  .respons {
    text-align: center;
  }
}

//Tablet
@media screen and (min-width: 767px) and (max-width: 1023px) {
  .respons {
    text-align: center;
  }
}

//DeskTop
@media screen and (min-width: 1024px) {
  .card-one {
    gap: 1.5rem !important;
  }
  .card-one-text {
    font-size: 46px;
    color: #000;
  }
  .card-two {
    gap: 0.8rem;
  }
  .respons {
    margin-left: 3rem !important;
    align-items: flex-start !important;
  }
}

.h1,
.h2,
.h3,
.h4,
.h5,
.h6,
h1,
h2,
h3,
h4,
h5,
h6 {
  margin-top: 0;
  margin-bottom: 0 !important;
  font-weight: 500;
  line-height: 1.1;
}
</style>
