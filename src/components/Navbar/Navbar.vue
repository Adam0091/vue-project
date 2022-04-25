<template>
    <div class="navbar">
      <nav>
        <RouterLink to="/">Home</RouterLink>
        <RouterLink to="/about">About</RouterLink>
        <RouterLink to="/login">Login</RouterLink>
      </nav>

      <slot name="controls"></slot>
    </div>
</template>

<style>
.navbar {
    padding: 0;
    width: 100%;
    display: flex;
    justify-content: space-between;
}
</style>