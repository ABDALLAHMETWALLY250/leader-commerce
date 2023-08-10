<template>
  <!-- Start Nav -->
  <nav
    class="navbar navbar-expand-lg w-100 fixed-top bg-light"
    style="z-index: 999"
  >
    <div class="container-fluid">
      <a class="navbar-brand" href="#">
        <img
          src="https://transvelo.github.io/freshcart/assets/images/freshcart-logo.svg"
          alt="logo"
        />
      </a>
      <!-- icons -->
      <div class="icons">
        <i
          class="fa-regular mr-4 fa-cart-shopping p-2 fa-beat fa-xl position-relative"
        >
          <span
            class="position-absolute top-0 start-100 translate-middle badge rounded-pill bg-danger"
            style="font-size: 10px"
          >
            {{ cart }}
          </span>
        </i>
        <i class="fa-regular fa-heart fa-beat p-2 fa-xl position-relative">
          <span
            class="position-absolute top-0 start-100 translate-middle badge rounded-pill bg-danger"
            style="font-size: 10px"
          >
            {{ heart }}
          </span>
        </i>
      </div>
      <button
        class="navbar-toggler"
        type="button"
        data-bs-toggle="collapse"
        data-bs-target="#navbarSupportedContent"
        aria-controls="navbarSupportedContent"
        aria-expanded="false"
        aria-label="Toggle navigation"
      >
        <span class="navbar-toggler-icon"></span>
      </button>
      <div class="collapse navbar-collapse" id="navbarSupportedContent">
        <ul class="navbar-nav mx-auto mb-2 mb-lg-0">
          <li class="nav-item">
            <a class="nav-link active" aria-current="page" href="#">Home</a>
          </li>
          <li class="nav-item">
            <a class="nav-link" href="#">Link</a>
          </li>
          <li class="nav-item dropdown">
            <a
              class="nav-link dropdown-toggle"
              href="#"
              role="button"
              data-bs-toggle="dropdown"
              aria-expanded="false"
            >
              Dropdown
            </a>
            <ul class="dropdown-menu">
              <li><a class="dropdown-item" href="#">Action</a></li>
              <li><a class="dropdown-item" href="#">Another action</a></li>
              <li><hr class="dropdown-divider" /></li>
              <li><a class="dropdown-item" href="#">Something else here</a></li>
            </ul>
          </li>
          <li class="nav-item">
            <a class="nav-link disabled">Disabled</a>
          </li>
        </ul>
        <form class="d-flex" role="search">
          <input
            class="form-control me-2"
            type="search"
            placeholder="Search"
            aria-label="Search"
          />
          <button class="btn btn-outline-success" type="submit">Search</button>
        </form>
      </div>
    </div>
  </nav>
  <br /><br />
  <!-- End Nav -->
  <div class="container">
    <div class="row my-5" v-if="product">
      <div class="col-lg-3 col-sm-6 col-md-6 mt-5">
        <div class="card">
          <img :src="product.image" class="card-img-top" alt="product-img" />
          <div class="card-body">
            <h5 class="card-title">{{ product.P_Name }}</h5>
            <hr />
            <p class="card-text">
              Product Dec : Lorem ipsum dolor sit amet, consectetur adipisicing
              elit. A vel ullam aliquid nisi suscipit doloribus sunt expedita,
              perspiciatis aperiam impedit laborum quod? Voluptatibus, in velit.
            </p>
          </div>
          <ul class="list-group list-group-flush">
            <li class="list-group-item">
              Product Rate :
              <div class="text-center">
                <v-rating
                  v-model="product.P_Rate"
                  color="warning"
                  readonly
                ></v-rating>
              </div>
            </li>
            <li class="list-group-item">
              <span>Product price:</span> {{ product.P_Price }}$
            </li>
          </ul>
          <div class="card-body">
            <v-btn class="v-btn" variant="outlined mx-1" @click="heart++">
              <i class="fa-regular fa-heart fa-beat p-2 fa-xl"></i>
            </v-btn>
            <v-btn class="v-btn" variant="outlined mx-1" @click="cart++">
              <i
                class="fa-regular fa-cart-shopping p-2 fa-beat fa-xl position-relative"
              ></i>
            </v-btn>

            <v-btn class="v-btn" variant="outlined mx-1" @click="cart++">
              <router-link to="/">  Back </router-link>
            </v-btn>
          </div>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
import axios from "axios";
export default {
  data() {
    return {
      product: null,
      cart: 0,
      heart: 0,
    };
  },
  mounted() {
    axios
      .get(
        "https://my-json-server.typicode.com/ABDALLAHMETWALLY250/product/products/" +
          this.$route.params.cat
      )
      .then((res) => {
        this.product = res.data;
      });
  },
};
</script>

<style lang="scss" scoped>
.row {
  display: flex;
  align-items: center;
  justify-content: center;
}
</style>
