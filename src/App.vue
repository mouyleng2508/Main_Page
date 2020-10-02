<template>
  <div>
    <v-app>
      <v-app-bar>
        <img height="100%" src="./assets/img/logo/logo.png" />
        <v-spacer></v-spacer>
        <div
          class="mx-2"
          style="border: 1px solid #aaa; border-radius: 10px; padding: 5px"
        >
          <v-icon class="mx-2">mdi-email</v-icon>
          <input style="border: none" placeholder="Email" />
        </div>
        <div
          class="mx-2"
          style="border: 1px solid #aaa; border-radius: 10px; padding: 5px"
        >
          <v-icon class="mx-2">mdi-form-textbox-password</v-icon>
          <input style="border: none" type="password" placeholder="password" />
        </div>
        <v-btn class="my-4" text>Log In</v-btn>
        <v-btn class="my-4" text>Sign Up</v-btn>
      </v-app-bar>
      <v-container mx-16 px-16 fill-height>
        <v-toolbar dense fixed>
          <v-btn to="/" text>
            <v-icon>mdi-home</v-icon>
          </v-btn>

          <v-spacer></v-spacer>

          <div>
            <v-icon class="mx-2">mdi-shopping-search</v-icon>
            <input style="border: none" placeholder="Search" />
          </div>
          <v-btn text @click="showFilter = !showFilter">
            <v-icon>mdi-filter-variant</v-icon> Filter</v-btn
          >
          <v-menu offset-y>
            <template v-slot:activator="{ on, attrs }">
              <v-btn text v-bind="attrs" v-on="on"> categories </v-btn>
            </template>
            <v-list>
              <v-list-item v-for="(item, index) in categories" :key="index">
                <v-list-item-title>{{ item.title }}</v-list-item-title>
              </v-list-item>
            </v-list>
          </v-menu>
        </v-toolbar>
        <v-row v-if="showFilter" justify="center" class="mt-4">
          <v-card elevation="0" class="mx-auto" width="600">
            <v-toolbar flat dense>
              <v-toolbar-title>
                <span class="subheading">Price</span>
              </v-toolbar-title>
            </v-toolbar>

            <v-card-text>
              <v-row class="mb-4" justify="space-between">
                <v-col class="text-left">
                  <span class="display-3 font-weight-light" v-text="100"></span>
                  <span class="subheading font-weight-light mr-1">$</span>
                </v-col>
              </v-row>

              <v-slider track-color="grey" always-dirty min="40" max="218">
              </v-slider>
            </v-card-text>
          </v-card>
          <v-card class="mx-auto elevation-0" width="600">
            <v-toolbar flat dense>
              <v-toolbar-title>
                <span class="subheading">Distance</span>
              </v-toolbar-title>
            </v-toolbar>

            <v-card-text>
              <v-row class="mb-4" justify="space-between">
                <v-col class="text-left">
                  <span class="display-3 font-weight-light" v-text="100"></span>
                  <span class="subheading font-weight-light mr-1">Km</span>
                </v-col>
              </v-row>

              <v-slider track-color="grey" always-dirty min="40" max="218">
              </v-slider>
            </v-card-text>
          </v-card>
        </v-row>
        <v-container>
          <router-view />
        </v-container>
      </v-container>
    </v-app>
  </div>
</template>

<script>
export default {
  name: "Home",
  data: () => ({
    showFilter: false,
    categories: [
      { title: "Book" },
      { title: "Clothes" },
      { title: "Food and Drink" },
      { title: "Utensil" },
    ],
    popular_products: [],
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
  methods: {},
};
</script>

<style>
p {
  font-size: 14px;
}
</style>
