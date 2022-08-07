<script setup lang="ts">
import { RouterLink, RouterView } from "vue-router";
</script>

<template>
  <header>
    <div class="wrapper">
      <div class="title">
        <img class="logo" src="trophy.png" />
        <h1>CATE Rankings</h1>
      </div>
      <nav>
        <RouterLink to="/">Rankings</RouterLink>
        <!-- <RouterLink to="/HolyBamboo">HolyBamboo</RouterLink> -->
      </nav>
    </div>
  </header>

  <RouterView />
</template>

<style scoped>

.title {
  display: flex;
  justify-content: center;
  font-size: x-large;
  align-items: center;
}

header {
  line-height: 1.5;
  max-height: 100vh;
}

.logo {
  display: block;
  height: 5rem;
}

nav {
  width: 100%;
  font-size: 12px;
  text-align: center;
  margin-top: 2rem;
}

nav a.router-link-exact-active {
  color: var(--color-text);
}

nav a.router-link-exact-active:hover {
  background-color: transparent;
}

nav a {
  display: inline-block;
  padding: 0 1rem;
  border-left: 1px solid var(--color-border);
}

nav a:first-of-type {
  border: 0;
}
</style>
