<template>
  <div class="home">
    <!-- Componente Home -->
    <Home />

    <!-- Componente RegisterForm -->
    <RegisterForm />

    <!-- Componente Toggle -->
    <Toggle />
  </div>
</template>

<script>
import { defineComponent } from "vue";
import Home from "./components/Home.vue";
import RegisterForm from "./components/RegisterForm.vue";
import Toggle from "./components/Toggle.vue";

export default defineComponent({
  name: "App",
  components: {
    Home,
    RegisterForm,
    Toggle,
  },
});
</script>

<style scoped>
@import url('https://fonts.googleapis.com/css2?family=Poppins:ital,wght@0,100;0,200;0,300;0,400;0,500;0,600;0,700;0,800;0,900;1,100;1,200;1,300;1,400;1,500;1,600;1,700;1,800;1,900&display=swap');


* {
    box-sizing: border-box;
    margin: 0;
    padding: 0;
    scroll-behavior: smooth;
    font-family: "Poppins", sans-serif;
    text-decoration: none;
    list-style: none;
}

body {
    min-height: 100vh;
    text-rendering: optimizeLegibility;
    -webkit-font-smoothing: antialiased;
    -moz-osx-font-smoothing: grayscale;
    overflow: hidden;
}

.home {
    display: flex;
    overflow: hidden;
    width: 100%; 
    min-height: 100vh;
    background-color: #181818;
}
</style>
