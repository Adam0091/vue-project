<script setup>
  import Navbar from "./components/Navbar/Navbar.vue"
</script>

<template>
  <Navbar>
    <template #controls>
      <button>Hi</button>
    </template>
  </Navbar>
  <RouterView />
</template>