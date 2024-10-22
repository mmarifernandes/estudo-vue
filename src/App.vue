<script setup>
import List from './components/List.vue'
// import TheWelcome from './components/TheWelcome.vue'
</script>

<template>
  <header>
    <!-- <img alt="Vue logo" class="logo" src="./assets/logo.svg" width="125" height="125" /> -->
    <h1>To-do list</h1>
  </header>

  <main>
  <List></List>
  </main>
</template>

<style scoped>
header {
  line-height: 1.5;
  display: flex;
  justify-content: center;
  margin-bottom: 2vh;
}

.logo {
  display: block;
  margin: 0 auto 2rem;
}
.h1{
  text-align: center !important;
}

@media (min-width: 1024px) {
  header {
    display: flex;
    place-items: center;
    padding-right: calc(var(--section-gap) / 2);
  }

  .logo {
    margin: 0 2rem 0 0;
  }

  header .wrapper {
    display: flex;
    place-items: flex-start;
    flex-wrap: wrap;
  }
}
</style>
