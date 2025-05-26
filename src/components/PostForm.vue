<script setup>
import { ref } from 'vue';

const props = defineProps({
    posts: Array
});

const emit = defineEmits(['create']);

let title = ref('');
let body = ref('');
let postTime = ref(Date.now());

function createPost() {
  let newPost = {
    title: title.value,
    time: postTime.value,
    body: body.value
  };
  
  emit('create', newPost);
  
  // Очищаем поля после создания
  title.value = '';
  body.value = '';
}


</script>


<template>
    <div class="creating-post-block">
    
    <input 
      :value="title"
      @input="title = $event.target.value" 
      type="text" class="title-input-for-creating-post" 
      placeholder="Какое название поста?">
    
    <input 
      :value="body" 
      @input="body = $event.target.value"
      type="text" class="body-input-for-creating-post" 
      placeholder="О чем пост?">  
    
    <button 
      class="button-for-creating-post" 
      @click="createPost()"
      >Создать
    </button>

  </div>
</template>


<style scoped>


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
}
</style>
