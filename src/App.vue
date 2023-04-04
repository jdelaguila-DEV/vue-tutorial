<template>
  <div class="container">
    <!-- jumbotron -->
    <Jumbutron title="Jumbutron" text="texto jumbutron" />

    <h1 class="py-3">App</h1>
    <ButtonCounter />
    <h1 class="py-3">Blog</h1>
    <BlogPost title="Post 1" text="texto 1" colorText="danger" backgroundColor="bg-info" />
    <BlogPost title="Post 2" text="texto 2" colorText="success" backgroundColor="bg-light" />
    <BlogPost title="Post 3" text="texto 3" colorText="warning" backgroundColor="bg-danger" />
    <BlogPost title="Post 3" text="texto 3" colorText="dark" backgroundColor="bg-primary" />

    <!-- consuming the api -->
    <h1 class="py-3">Api</h1>
    <div v-for="p in post" :key="p.id">
      <BlogPost :title="p.title" :text="p.body" colorText="dark" backgroundColor="bg-light" />
    </div>


  </div>
</template>

<script setup lang="ts">
import BlogPost from './components/BlogPost.vue';
import ButtonCounter from './components/ButtonCounter.vue';
import Jumbutron from './components/Jumbutron.vue';
import axios from 'axios';
import { ref } from 'vue';

const post: any = ref([]);

const getPost = async () => {
  try {
    const response = await axios.get('https://jsonplaceholder.typicode.com/posts');
    post.value = response.data;
  } catch (error) {
    console.error(error);
  }
}

getPost();

</script>

<style scoped></style>