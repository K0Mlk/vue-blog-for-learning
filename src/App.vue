<script setup>
import { ref } from 'vue';
import PostForm from './components/PostForm.vue';
import PostList from './components/PostList.vue';


let postTime = ref(Date.now());
// let title = ref('');
// let body = ref('');

let posts = ref([
  {
    // id: 1,
    title: 'New world',
    time: postTime,
    body: 'Soderjimoe posta. O, zdravstvuy divniy noviy MIR!!'
  },
  {
    // id: 2,
    title: 'KukushkaFM',
    time: postTime,
    body: 'Kto eto pridumal suka!!'
  },
  {
    // id: 3,
    title: 'Anime dlya Peti',
    time: postTime,
    body: 'Pizdec, che za novosti!!'
  }  
]);

// function createPost() {
  
//   let newPost = {
//     // id: 3,
//     title: title.value,
//     time: postTime,
//     body: body.value
//   };

//   return posts.value.push(newPost);   
// }
</script>


<template>
  <div class="app">
    <PostForm />
    <PostList
      v-for="post in posts"
      :title="post.title"
      :time="post.time"
      :body="post.body" 
    />
  </div>
</template>


<style scoped>
/* .post {
  padding: 15px;
  margin: 15px;
  margin-top: 25px;
  border: solid 4px snow;
  border-radius: 18px;
}

.title-input-for-creating-post,
.body-input-for-creating-post,
.button-for-creating-post {
  width: 100%;
  padding: 10px 15px;
  margin: 15px 0 15px 0;
  border: solid 4px snow;
  border-radius: 18px;
}

.button-for-creating-post {
  justify-content: end;
  background-color: black;
  color: snow;
}

.button-for-creating-post:hover {
  border-color: thistle;
}

.title-input-for-creating-post:active,
.body-input-for-creating-post:active {
  border-color: thistle;
}

.creating-post-block {
  display: flex;
  flex-direction: column;
} */
</style>
