<script setup>
 import { reactive, ref } from "@vue/reactivity";
  const isAuth = ref(null);
  isAuth.value = localStorage.getItem("token") ? true : false;

  const signout = () => {
    isAuth.value = false;
    localStorage.removeItem("token");
  }
</script>


<template>
  <div class="home">
    <p v-if="isAuth">
      <h1> Hello user</h1>
      <button @click="signout">logout</button>
    </p>
    <p v-else>Back</p>
  </div>
</template>
