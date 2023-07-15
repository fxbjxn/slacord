<script setup>
// import { RouterLink, RouterView } from "vue-router";
import MessageBox from "./components/MessageBox.vue";
import HeaderBox from "./components/HeaderBox.vue";
import ConnectionState from "./components/ConnectionState.vue";
</script>

<template>
  <ConnectionState />
  <nav>THIS SHOULD BE LEFT SIDE</nav>
  <div class="wrapper">
    <div class="chat">
      <HeaderBox />
      <MessageBox />
    </div>
    <!-- <nav>
        <RouterLink to="/">Home</RouterLink>
        <RouterLink to="/about">About</RouterLink>
      </nav> -->
  </div>
  <nav>THIS SHOULD BE RIGHT SIDE</nav>

  <!-- <RouterView /> -->
</template>

<style scoped>
nav {
  background-color: red;
  max-width: 400px;
  min-width: 200px;
}
.wrapper {
  padding: 20px;
}

/* header {
  line-height: 1.5;
  max-height: 100vh;
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

  /* nav {
    text-align: left;
    margin-left: -1rem;
    font-size: 1rem;

    padding: 1rem 0;
    margin-top: 1rem;
  } */
/* } */
</style>
