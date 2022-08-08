<template>
  <div>
    <Navbar />
    <v-container>
      <v-card class="mt-5">
        <v-card-title class="card-title display-1">Book Details</v-card-title>
        <v-container>
          <v-row>
            <v-col lg="3" cols="12">
              <v-img
                width="200"
                height="250"
                :src="
                  `https://bookcart.azurewebsites.net/Upload/` + coverFileName
                "
              />
            </v-col>
            <v-col lg="4" cols="12">
              <v-simple-table>
                <template v-slot:default>
                  <tbody>
                    <tr>
                      <td class="subtitle-1 title-td">Title</td>
                      <td class="subtitle-1">{{ title }}</td>
                    </tr>

                    <tr>
                      <td class="subtitle-1 title-td">Author</td>
                      <td class="subtitle-1">{{ author }}</td>
                    </tr>

                    <tr>
                      <td class="subtitle-1 title-td">Category</td>
                      <td class="subtitle-1">{{ category }}</td>
                    </tr>

                    <tr>
                      <td class="subtitle-1 title-td">Price</td>
                      <td class="subtitle-1">$ {{ price }}</td>
                    </tr>
                    <tr>
                      <v-btn
                        class="mt-4"
                        color="primary"
                        depressed
                      >
                        <v-icon dense>mdi-cart</v-icon>
                        <span> Add to Cart </span>
                      </v-btn>
                    </tr>
                  </tbody>
                </template>
              </v-simple-table>
            </v-col>
          </v-row>
        </v-container>
      </v-card>
      <!-- item two -->
      <v-card class="mt-5">
        <v-card-title class="card-title display-1">Similar Books</v-card-title>
        <v-container>
          <v-slide-group
            v-model="model"
            class="pa-4"
            active-class="success"
            show-arrows
          >
            <v-slide-item v-for="(book ,index) in books" :key="index">
              <v-card
                class="ma-4"
                height="400"
                width="210"
                @click="toggle"
              >

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
                        width="210"
                        v-bind="attrs"
                        v-on="on"
                        :src="
                          `https://bookcart.azurewebsites.net/Upload/` +
                          book.coverFileName
                        "
                      />
                    </router-link>
                  </template>
                  <span>hello</span>
                </v-tooltip>

              </v-card>
            </v-slide-item>
          </v-slide-group>
        </v-container>
      </v-card>
    </v-container>
  </div>
</template>

<script>
import Navbar from "../Navbar.vue";

export default {
  name: "BookItem",
  components: {
    Navbar,
  },
  data() {
    return {
      title: this.$route.params.title,
      author: this.$route.params.author,
      category: this.$route.params.category,
      price: this.$route.params.price,
      coverFileName: this.$route.params.coverFileName,
      books: [],
    };
  },
  created() {
    this.$store.dispatch("allBook").then((res) => {
      // this.books = res.data;
      var arr = res.data;

      // Getting a random array key
      var rand = Math.floor(Math.random() * arr.length);

      this.books = arr[rand]
      console.log(this.books);
    });
  },
};
</script>

<style scoped>
.card-title {
  background-color: #ff4081;
}
.title-td {
  font-weight: 700;
}
</style>