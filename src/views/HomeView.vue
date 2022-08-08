<template>
  <div>
    <Navbar />
    <router-view />
    <v-container>
      <v-row>
        <v-col lg="3" cols="12">
          <LeftMenu />
        </v-col>
        <v-col lg="9" cols="12">
          <v-row>
            <!-- start items -->
            <v-col lg="3" cols="6" v-for="(book, index) in books" :key="index">
              <v-card class="mx-auto mt-5">
                <v-tooltip bottom>
                  <template v-slot:activator="{ on, attrs }">
                    <router-link
                      :to="{
                        name: 'bookItem',
                        params: {
                          title: book.title,
                          author: book.author,
                          category: book.category,
                          price: book.price,
                          coverFileName: book.coverFileName,
                        },
                      }"
                    >
                      <v-img
                        height="250"
                        width="200"
                        v-bind="attrs"
                        v-on="on"
                        :src="
                          `https://bookcart.azurewebsites.net/Upload/` +
                          book.coverFileName
                        "
                      />
                    </router-link>
                  </template>
                  <span>{{ book.title }}</span>
                </v-tooltip>
                <v-btn
                  class="favorite-item"
                  icon
                  @click="favoriteList = !favoriteList"
                  v-show="isLoggedIn"
                >
                  <v-icon color="white" v-show="favoriteList === false"
                    >mdi-heart-outline</v-icon
                  >
                  <v-icon color="red" v-show="favoriteList">mdi-heart</v-icon>
                </v-btn>

                <v-card-title>
                  <router-link class="subtitle-2 title-text-book" to="/">{{
                    book.title
                  }}</router-link>
                </v-card-title>

                <v-card-text>
                  <div class="text-subtitle-1">$ {{ book.price }}</div>
                </v-card-text>

                <v-divider></v-divider>

                <v-card-actions>
                  <v-btn
                    class="mx-3"
                    color="primary"
                    depressed
                  >
                    <v-icon dense>mdi-cart</v-icon>
                    <span> Add to Cart </span>
                  </v-btn>
                </v-card-actions>
              </v-card>
            </v-col>
            <!-- end items -->
          </v-row>
        </v-col>
      </v-row>
    </v-container>
  </div>
</template>

<script>
import Navbar from "@/components/Navbar.vue";
import LeftMenu from "@/components/LeftMenu.vue";

export default {
  name: "Home",
  components: {
    Navbar,
    LeftMenu,
  },
  data() {
    return {
      favoriteList: false,
      books: "",
    };
  },
  computed: {
    isLoggedIn() {
      return window.localStorage.getItem("token");
    },
  },
  methods: {
    favorite_icon_counter() {
      this.favoriteList = true;
    },
  },
  created() {
    this.$store.dispatch("allBook").then((res) => {
      this.books = res.data;
    });
  },
};
</script>

<style scoped>
.favorite-item {
  position: absolute;
  top: 5px;
  right: 5px;
}
.title-text-book {
  height: 21px;
  text-overflow: ellipsis;
  white-space: nowrap;
  overflow: hidden;
}
</style>