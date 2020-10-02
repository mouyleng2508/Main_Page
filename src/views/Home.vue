<template>
  <v-container>
    <span>
      <v-carousel hide-delimiters>
        <v-carousel-item
          v-for="(item, i) in slide"
          :key="i"
          :src="item.src"
        ></v-carousel-item>
      </v-carousel>
    </span>

    <span v-if="search_result != null">
      <h4>SEARCH RESULT</h4>
      <v-row justify="center" no-gutters>
        <v-card
          class="mx-2"
          width="250"
          v-for="item in search_result"
          :key="item.name"
          @click="details"
        >
          <v-img
            src="https://cdn.vuetifyjs.com/images/cards/cooking.png"
          ></v-img>
          <v-card-title>
            <h6>Name:</h6>
            <v-spacer></v-spacer>
            <h5>{{ item.name }}</h5></v-card-title
          >
          <v-card-text>
            <v-row align="center" class="mx-0">
              <v-rating
                :value="item.star"
                color="amber"
                dense
                half-increments
                readonly
                size="14"
              ></v-rating>
            </v-row>
          </v-card-text>
        </v-card>
      </v-row>
    </span>

    <h4>POPULAR PRODUCTS</h4>
    <v-row no-gutters>
      <v-card
        class="mx-2"
        width="250"
        v-for="item in popular_products"
        :key="item.name"
        @click="details"
      >
        <v-img src="https://cdn.vuetifyjs.com/images/cards/cooking.png"></v-img>
        <v-card-title>
          <h6>Name:</h6>
          <v-spacer></v-spacer>
          <h5>{{ item.name }}</h5></v-card-title
        >
        <v-card-text>
          <v-row align="center" class="mx-0">
            <v-rating
              :value="item.star"
              color="amber"
              dense
              half-increments
              readonly
              size="14"
            ></v-rating>
          </v-row>
        </v-card-text>
      </v-card>
    </v-row>
  </v-container>
</template>

<script>
export default {
  name: "Home",
  data: () => ({
    showFilter: false,
    search_result: null,
    categories: [
      { title: "Click Me" },
      { title: "Click Me" },
      { title: "Click Me" },
      { title: "Click Me 2" },
    ],
    popular_products: [
      {
        name: "News Agent",
        star: 4,
      },
      {
        name: "News Agent2",
        star: 4,
      },
      {
        name: "News Agent1",
        star: 4,
      },
      {
        name: "MITDTLA",
        star: 4,
      },
      {
        name: "Starbuck",
        star: 4,
      },
      {
        name: "Book Store",
        star: 4,
      },
    ],
    slide: [
      {
        src: "https://cdn.vuetifyjs.com/images/carousel/sky.jpg",
      },
      {
        src: "https://cdn.vuetifyjs.com/images/carousel/bird.jpg",
      },
      {
        src: "https://cdn.vuetifyjs.com/images/carousel/planet.jpg",
      },
    ],
  }),
  components: {},
  methods: {
    details() {
      this.$router.push({ path: "/details" });
    },
    search(){
      this.search_result = [
        {
        name: "News Agent",
        star: 4,
      },
      {
        name: "News Agent2",
        star: 4,
      },
      {
        name: "News Agent1",
        star: 4,
      },
      {
        name: "MITDTLA",
        star: 4,
      },
      {
        name: "Starbuck",
        star: 4,
      },
      {
        name: "Book Store",
        star: 4,
      },
      ]
    }
  },
};
</script>

<style scoped>
p {
  font-size: 14px;
}
</style>
