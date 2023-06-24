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
        <i class="fa-regular mr-5 fa-cart-shopping p-2 fa-beat fa-xl">
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
  <!-- End Nav -->

  <div class="my-5 text-start">
    <div class="container">
      <h3>New Products</h3>
      <div class="row">
        <div class="col-lg-6 col-sm-12 col-md-6">
          <p>New products with updated stocks</p>
        </div>
        <div class="col-lg-6 col-sm-12 col-md-6">
          <ul class="ul">
            <li>
              <h6>Fruits & Vegetables</h6>
            </li>

            <li class="mx-3">
              <h6>Snacks & Munchies</h6>
            </li>

            <li class="mx-3">
              <h6>Tee,Coffe & Drink</h6>
            </li>

            <li class="mx-3">
              <h6>Cold Drink</h6>
            </li>

            <li class="mx-3">
              <h6>Bakery Biscuts</h6>
            </li>
          </ul>
        </div>
      </div>
      <div class="row my-5" v-if="Products">
        <div
          class="col-lg-3 col-sm-6 col-md-6 mt-5"
          v-for="product in Products"
          :key="product"
        >
          <div class="card">
            <img :src="product.image" class="card-img-top" alt="product-img" />
            <div class="card-body">
              <h5 class="card-title">{{ product.P_Name }}</h5>
              <hr />
              <p class="card-text">
                Product Dec : Lorem ipsum dolor sit amet, consectetur
                adipisicing elit. A vel ullam aliquid nisi suscipit doloribus
                sunt expedita, perspiciatis aperiam impedit laborum quod?
                Voluptatibus, in velit.
              </p>
            </div>
            <ul class="list-group list-group-flush">
              <li class="list-group-item">
                Product Rate :
                <v-rating
                  :v-model="product.P_Rate"
                  color="white"
                  active-color="yellow-accent-4"
                  half-increments
                  hover
                  size="18"
                ></v-rating>
              </li>
              <li class="list-group-item">
                Product price: {{ product.P_Price }}$
              </li>
            </ul>
            <div class="card-body text-center">
              <v-btn class="v-btn" variant="outlined mx-1" @click="heart++">
                <i class="fa-regular fa-heart fa-beat p-2 fa-xl"></i>
              </v-btn>
              <v-btn class="v-btn" variant="outlined mx-1" @click="heart++">
                <router-link
                  :to="`/details/${product.id}`"
                  class="border rounded"
                >
                  More Details
                </router-link>
              </v-btn>
            </div>
          </div>
        </div>
      </div>
    </div>
  </div>
</template>
<script>
import axios from "axios";
export default {
  data: () => ({
    selection: 1,
    cart: 0,
    heart: 0,
    Products: null,
  }),

  mounted() {
    axios
      .get(
        "https://my-json-server.typicode.com/ABDALLAHMETWALLY250/product/products/"
      )
      .then((res) => {
        this.Products = res.data;
      });
  },
};
</script>

<style lang="scss" scoped>
.icons {
  i {
    cursor: pointer;
  }
  .fa-cart-shopping {
    color: gray;
  }
  .fa-cart-shopping:hover {
    color: green;
  }

  .fa-heart {
    color: gray;
  }
  .fa-heart:hover {
    color: red;
  }
}
.card-body:hover {
  .fa-cart-shopping:hover {
    color: green;
  }
  .fa-heart:hover {
    color: red;
  }
}
h3 {
  color: #001e2b;
}
@media screen and (max-width: 767px) {
  .ul {
    list-style: none;
    display: flex;
    align-items: baseline;
    justify-content: center;
    padding-left: 0;
    li h6 {
      font-size: 10px;
    }
    li:hover h6 {
      color: green;
      cursor: pointer;
    }
  }
}
@media screen and (min-width: 767px) and (max-width: 1023px) {
  .ul {
    list-style: none;
    display: flex;
    align-items: baseline;
    justify-content: center;
    li h6 {
      font-size: 13px;
    }
    li:hover h6 {
      color: green;
      cursor: pointer;
    }
  }
}
@media screen and (min-width: 1024px) {
  .ul {
    list-style: none;
    display: flex;
    align-items: baseline;
    justify-content: center;
    li h6 {
      font-size: 13px;
    }
    li:hover h6 {
      color: green;
      cursor: pointer;
    }
  }
}
.dialog-bottom-transition-enter-active,
.dialog-bottom-transition-leave-active {
  transition: transform 0.2s ease-in-out;
}
</style>
