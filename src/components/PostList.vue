<script setup>

defineProps(['title', 'time', 'body'])

</script>


<template>
  
  <div class="post">
    <div class="post-title"><strong>Название: </strong>{{ title }}</div>
    <div class="post-time"><strong>Дата: </strong> {{ time }}</div>
    <div class="post-body"><strong>Описание: </strong><br>{{ body }}</div>
  </div>
  
</template>


<style scoped>
.post {
  padding: 15px;
  margin: 15px;
  margin-top: 25px;
  border: solid 4px snow;
  border-radius: 18px;
}

</style>
