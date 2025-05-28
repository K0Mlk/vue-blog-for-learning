<script setup>

const props = defineProps(['title', 'time', 'body']);
const emit = defineEmits(['delete']);


function deletePostButton()
{
    let oldPost = {
        title: props.title, 
        time: props.time, 
        body: props.body
    }
    emit('delete', oldPost);
}

</script>


<template>
  
  <div class="post">

    <div class="post-data">
        <div class="post-title"><strong>Название: </strong>{{ title }}</div>
        <div class="post-time"><strong>Дата: </strong> {{ time }}</div>
        <div class="post-body"><strong>Описание: </strong><br>{{ body }}</div>
    </div>

    <button
        class="button-for-deleting-post"
        @click="deletePostButton"
        >Удалить
    </button>
  </div>
  
</template>


<style scoped>
.post {
    display: flex;
    padding: 15px;
    margin: 15px;
    margin-top: 25px;
    border: solid 4px rgba(216, 252, 215, 0.849);
    border-radius: 14px;
}

.post-data {
    flex-grow: 1
}

.button-for-deleting-post {
    /* justify-content: flex-end; */
    background-color: rgba(0, 0, 0, 0.959);
    color: green;
    border-radius: 8px;
    padding: 0 18px 0 18px;
    margin: 10px;
}

.button-for-deleting-post:hover {
    border-color: green;
}

</style>
