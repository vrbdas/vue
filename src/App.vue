<script setup>
import UserComp from './components/UserComp.vue';
</script>

<template>
  <div class="form">
  <input type="text" placeholder="Имя" v-model="userName">
  <input type="password" placeholder="Пароль" v-model="userPassw">
  <input type="email" placeholder="Email" v-model="userEmail">
  <button @click.prevent="send">Отправить</button>
  <p class="error">{{ error }}</p>
</div>
<div v-if="users.length == 0">
  <h3>Нет пользователей</h3>
</div>
  <UserComp v-for="(user, index) in users" :key="index" :user="user" :index="index" :users="users" />
</template>

<script>
export default {
  data() {
    return {
      users: [],
      userName: '',
      userPassw: '',
      userEmail: '',
      error: '',
    }
  },
  
  methods: {
    send() {
      if (this.userName.length < 2) {
        this.error = 'Имя слишком короткое';
        return;
     }
     if (this.userPassw.length < 3) {
      this.error = 'Пароль слишком короткий';
      return;
     } 
     if (this.userEmail.length === 0) {
      this.error = 'Некорректный адрес Email';
      return;
     }
    this.users.push({
      name: this.userName,
      passw: this.userPassw,
      email: this.userEmail,
    });
    this.userName = '';
    this.userPassw = '';
    this.userEmail = '';
    this.error = '';
    },
  },
}
</script>

<style scoped>
  .form {
    width: 250px;
    padding: 10px;
    display: flex;
    flex-direction: column;
    gap: 10px;
  }
  .hide {
    display: none;
  }
  button {
    width: 50%;
  }
  .error {
    color: red;
  }
</style>
