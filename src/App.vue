<template>
  <div class="container">
    <!-- jumbotron -->
    <Jumbutron title="Jumbutron" text="texto jumbutron" />

    <!-- counter -->
    <h1 class="py-3">Counter</h1>
    <ButtonCounter color="success" />

    <!-- favorites -->
    <h1 class="py-3">Favorites</h1>
    <h3>My favorite posts: <span class="text-warning"> {{ favorite }} </span></h3>

    <!-- blog -->
    <h1 class="py-3">Blog</h1>
    <BlogPost :id="1" title="Post 1" body="texto 1" colorText="success" @changeFavoriteName="changeFavorite" />

    <!-- pagination -->
    <Pagination :next="next" :previus="previus" />

    <!-- consuming the api -->
    <div v-for="p in posts.slice(init, limit)" :key="p.id">
      <BlogPost :id="p.id" :title="p.title" :body="p.body" @changeFavoriteName="changeFavorite" />
    </div>

  </div>
</template>

<script setup lang="ts">

import BlogPost from './components/BlogPost.vue';
import ButtonCounter from './components/ButtonCounter.vue';
import Jumbutron from './components/Jumbutron.vue';
import axios from 'axios';
import { ref } from 'vue';
import Pagination from './components/Pagination.vue';


const posts: any = ref([]);
const qtyPage = 3;
const init = ref(0)
const limit = ref(qtyPage)



// get the api with axios//

const getPost = async () => {
  try {
    const response = await axios.get('https://jsonplaceholder.typicode.com/posts');
    posts.value = response.data;
  } catch (error) {
    console.error(error);
  }
}

getPost();

//emit favorites posts //

const favorite = ref("");

const changeFavorite = (title: any) => {
  favorite.value = title;
}

// pagination //

const next = () => {
  init.value = init.value + qtyPage;
  limit.value = limit.value + qtyPage;
}

const previus = () => {
  init.value = init.value - qtyPage;
  limit.value = limit.value - qtyPage;
}


</script>

<style scoped></style>