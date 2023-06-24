<template>
  <div class="home">
    <NavComp />
    <HomeComp />
    <!-- <CardsComp /> -->
  </div>
</template>

<script>
// @ is an alias to /src
import NavComp from "@/components/NavComp.vue";
import HomeComp from "@/components/HomeComp.vue";
// import CardsComp from "@/components/CardsComp.vue";

export default {
  name: "HomeView",
  components: {
    NavComp,
    HomeComp,
    // CardsComp,
  },
};
</script>
