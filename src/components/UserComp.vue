<!-- eslint-disable no-unused-vars -->
<script setup>
const props = defineProps(['user', 'index']);
</script>

<template>
  <div class="user">
    <h3>Пользователь {{ index }}:</h3>
    Имя: {{ user.name }}<br>
    Пароль: {{ user.passw }}<br>
    Email: {{ user.email }}<br>
  </div>
</template>

<script>
export default {
  // props: ['user', 'index'],
}
</script>

<style scoped>
  .user {
    padding: 10px;
    background-color:aqua;
    width: 250px;
    border-radius: 10px;
    margin-bottom: 10px;
  }
</style>