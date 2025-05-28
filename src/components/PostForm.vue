<script setup>
import { ref } from 'vue';

// const props = defineProps({
//     posts: Array
// });

const emit = defineEmits(['create']);

let title = ref('');
let body = ref('');

function createPostButton() {
    let newPost = {
      title: title.value,
      body: body.value
    };
    
    emit('create', newPost);
    
    title.value = '';
    body.value = '';
}


</script>


<template>
    <div class="creating-post-block">
    
    <input 
      v-model="title"
      type="text" class="title-input-for-creating-post" 
      placeholder="Какое название поста?">
    
    <input 
      v-model="body" 
      type="text" class="body-input-for-creating-post" 
      placeholder="О чем пост?">  
    
    <button 
      class="button-for-creating-post" 
      @click="createPostButton"
      >Создать
    </button>

  </div>
</template>


<style scoped>


.title-input-for-creating-post,
.body-input-for-creating-post {
    width: 100%;
    padding: 10px 15px;
    margin: 15px 0 15px 0;
    border: solid 4px rgb(12, 4, 4);
    border-radius: 14px;
    border-color: rgb(216, 252, 215);
    

}

.button-for-creating-post {
    width: 100%;
    padding: 10px 15px;
    margin: 15px 0 15px 0;
    background-color: rgba(0, 0, 0, 0.959);
    border-radius: 8px;
}

.button-for-creating-post {
    justify-content: end;
    background-color: black;
    color: green;
    border-color: rgb(216, 252, 215);
}

.button-for-creating-post:hover {
    border-color: green;
}

.title-input-for-creating-post:active,
.body-input-for-creating-post:active {
    border-color: rgb(4, 12, 4);
}

.creating-post-block {
    display: flex;
    flex-direction: column;
}
</style>
