<!-- eslint-disable no-unused-vars -->
<script setup>
const props = defineProps(['user', 'index', 'users']);
</script>

<template>
  <div class="user" @mouseover="btnAppear()" @mouseout="btnDisappear()">
    <h3>Пользователь {{ index }}:</h3><br>
    Имя: {{ user.name }}<br>
    Пароль: {{ user.passw }}<br>
    Email: {{ user.email }}<br>
    <button @click="deleteUser(index)" class="delete-btn" :class="btnClass"><svg xmlns="http://www.w3.org/2000/svg"  viewBox="0 0 24 24" width="18px" height="18px"><path d="M 10.806641 2 C 10.289641 2 9.7956875 2.2043125 9.4296875 2.5703125 L 9 3 L 4 3 A 1.0001 1.0001 0 1 0 4 5 L 20 5 A 1.0001 1.0001 0 1 0 20 3 L 15 3 L 14.570312 2.5703125 C 14.205312 2.2043125 13.710359 2 13.193359 2 L 10.806641 2 z M 4.3652344 7 L 5.8925781 20.263672 C 6.0245781 21.253672 6.877 22 7.875 22 L 16.123047 22 C 17.121047 22 17.974422 21.254859 18.107422 20.255859 L 19.634766 7 L 4.3652344 7 z"/></svg></button>
  </div>
</template>

<script>
export default {
  data() {
    return {
      btnClass: 'hide',
    }
  },
  methods: {
    btnAppear() {
      this.btnClass = 'show';
    },
    btnDisappear() {
      this.btnClass = 'hide';
    },
    deleteUser(index) {
      this.users.splice(index, 1);
    },
  }
}
</script>

<style scoped>
  .user {
    padding: 10px;
    background-color:aqua;
    width: 250px;
    border-radius: 10px;
    margin-bottom: 10px;
    position: relative;
    font-size: 14px;
  }
  h3 {
    margin: 0;
    padding: 0;
  }
  .delete-btn {
    background-color: aqua;
    border: none;
    position: absolute;
    top: 10px;
    right: 10px;
    cursor: pointer;
  }
  .show {
    display: '';
  }
  .hide {
    display:none;
  }
</style>