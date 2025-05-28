<script setup>
import { ref } from 'vue';
import PostForm from './components/PostForm.vue';
import PostList from './components/PostList.vue';



let posts = ref([
  {
    // id: 1,
    title: 'New world',
    time: Date.now(),
    body: 'Soderjimoe posta. O, zdravstvuy divniy noviy MIR!!'
  },
  {
    // id: 2,
    title: 'KukushkaFM',
    time: Date.now(),
    body: 'Kto eto pridumal suka!!'
  },
  {
    // id: 3,
    title: 'Anime dlya Peti',
    time: Date.now(),
    body: 'Pizdec, che za novosti!!'
  }  
]);

const createPost = (newPost) => {
  posts.value.push({
    ...newPost,
    time: Date.now()
  });
};

const deletePost = (oldPost) => {
  posts.value = posts.value.filter(post => post.title !== oldPost.title);
}

</script>


<template>
  <div class="app">
    <PostForm
      @create="createPost"
    />

    <div v-for="post in posts" :key="post.title + post.time">
      <PostList
        :title="post.title"
        :time="post.time"
        :body="post.body"
        @delete="deletePost" 
      />
    </div>
    
  </div>
</template>


<style scoped>

</style>
