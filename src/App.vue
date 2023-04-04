<template>
  <div class="container">
    <h1 class="py-3">App</h1>
    <ButtonCounter />
    <h1 class="py-3">Blog</h1>
    <BlogPost title="Post 1" text="texto 1" colorText="info" backgroundColor="bg-info" />
    <BlogPost title="Post 2" text="texto 2" colorText="success" backgroundColor="bg-light" />
    <BlogPost title="Post 3" text="texto 3" colorText="warning" backgroundColor="bg-danger" />
    <BlogPost title="Post 3" text="texto 3" colorText="dark" backgroundColor="bg-primary" />

    <!-- consuming the api -->
    <h1 class="py-3">Api</h1>
    <div v-for="post in posts">
      <BlogPost title="post.title" text="post.body" colorText="info" backgroundColor="bg-info" />
    </div>


  </div>
</template>

<script setup lang="ts">
import BlogPost from './components/BlogPost.vue';
import ButtonCounter from './components/ButtonCounter.vue';

// function for consuming an api

const Api = async () => {
  const response = await fetch('https://jsonplaceholder.typicode.com/posts');
  const data = await response.json();
  console.log(data)
  return data;
};

const posts = Api();


</script>

<style scoped></style>