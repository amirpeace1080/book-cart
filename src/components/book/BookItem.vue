<template>
  <v-container>
    <v-card class="mt-5">
      <v-card-title class="pink--text">hello world</v-card-title>
      <v-container>
        <v-row>
          <v-col lg="3" cols="12">
            <v-img
              width="200"
              height="250"
              :src="`https://bookcart.azurewebsites.net/Upload/` +coverFileName"
             />
          </v-col>
          <v-col lg="3" cols="12"></v-col>
        </v-row>
      </v-container>
    </v-card>
  </v-container>
</template>

<script>
export default {
  name: "BookItem",
  data() {
    return {
      title: this.$route.params.title,
      author: this.$route.params.author,
      category: this.$route.params.category,
      price: this.$route.params.price,
      coverFileName: this.$route.params.coverFileName,
    };
  },
};
</script>

<style>
</style>