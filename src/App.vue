<script setup lang="ts">
import { RouterLink, RouterView } from 'vue-router'

</script>
  
<template>
<div id="layout">
  <header>
    <div class="wrapper">
      <nav>
        <RouterLink :to="{ name: 'event-list-view'}" >Home</RouterLink> |
        <RouterLink :to="{ name: 'event-list-view'}">Event</RouterLink> |
        <RouterLink :to="{ name: 'student'}">StudentList</RouterLink> |
        <RouterLink :to="{ name: 'about'}">About</RouterLink>
      </nav>
      </div>
    </header>

    <router-link 
    v-for="size in [2, 3, 4, 5]"
    :key="size"
    :to="{ query: { ...$route.query, size: size, page: 1}}"
    :class="{ 'active-size': ($route.query.size  || 2 ) == size}"
    >
     {{ size }} per page
    </router-link>
    

    <RouterView />

  </div>
</template>

<style>
#layout {
  font-family: Avenir, Arial, Helvetica, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
}
nav {
  padding: 30px;
}

nav a {
font-weight: bold;
color: #2c3e50;
}
nav a.router-link-exact-active {
  color: #42b983;
}

h2 {
  font-size: 20px;
}
</style>
