<template>
    <v-app-bar app color="deep-purple accent-4" dark>
      <v-toolbar-title class="text-h5"> Paul's Portfolio </v-toolbar-title>
      <v-spacer></v-spacer>
      <v-btn icon v-if="isMobile" @click="drawer = !drawer">
        <v-icon>mdi-menu</v-icon>
      </v-btn>
      <nav v-else>
        <RouterLink class="router-link" to="/">Home</RouterLink>
        <RouterLink class="router-link" to="/about">About</RouterLink>
        <RouterLink class="router-link" to="/projects">Projects</RouterLink>
        <RouterLink class="router-link" to="/reviews">Reviews</RouterLink>
        <RouterLink class="router-link" to="/contact">Contact</RouterLink>
      </nav>
    </v-app-bar>
  </template>
  
  <script>
  export default {
    name: "HeaderVue",
    data() {
      return {
        drawer: false,
        isMobile: false,
      };
    },
    methods: {
      handleResize() {
        this.isMobile = window.innerWidth < 768;
      },
    },
  };
  </script>
  
  <style scoped>
  nav {
    margin-right: 10px;
    text-transform: uppercase;
    letter-spacing: 0.05em;
  }
  
  .router-link {
    padding: 10px;
    transition: background-color 0.3s ease;
  }
  
  .router-link:hover {
    background-color: rgba(248, 0, 0, 0.1);
  }
  
  v-app-bar {
    box-shadow: 0 4px 6px rgba(0, 0, 0, 0.1);
  }
  
  v-toolbar-title {
    display: flex;
    align-items: center;
    gap: 10px;
  }
  </style>
  