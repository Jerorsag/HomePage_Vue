<template>
    <div :class="['container', { active: isActive }]">
      <div class="toggle-container">
        <div class="toggle">
          <!-- Panel izquierdo -->
          <div 
            class="toggle-panel toggle-left" 
            @mouseenter="setActive(false)"
          >
            <span>Logo</span>
            <h1>Name App</h1>
            <p>Slogan</p>
          </div>
  
          <!-- Panel derecho -->
          <div 
            class="toggle-panel toggle-right" 
            @mouseenter="setActive(true)"
          >
            <h1>¡Empieza el registro de tu parqueadero!</h1>
            <span>Logo</span>
          </div>
        </div>
      </div>
    </div>
  </template>
  
  <script>
  import { defineComponent, ref } from "vue";
  
  export default defineComponent({
    name: "Toggle",
    setup() {
      const isActive = ref(false);
  
      // Función para alternar el estado de `isActive`
      const setActive = (value) => {
        isActive.value = value;
      };
  
      return {
        isActive,
        setActive,
      };
    },
  });
  </script>
  
  <style scoped>
.toggle-container{
    position: absolute;
    top: 0;
    right: 0;
    width: 40%;
    height: 100%;
    overflow: hidden;
    transition: all 0.6s ease-in-out;
    border-radius: 150px 0 0 100px;
    z-index: 1000;
}

.container.active .toggle-container{
    transform: translateX(-70%);
    border-radius: 0 150px 100px 0;
    width: 60%;
}

.toggle {
    background-color: #332ff6;
    height: 100%;
    background: linear-gradient(to right, #4f4cff, #322ff3);
    color: #fff;
    position: relative;
    left: -100%;
    height: 100%;
    width: 200%;
    transform: translateX(0);
    transition: all 0.6s ease-in-out;
}

.container.active .toggle{
    transform: translateX(50%);
}

.toggle-panel{
    position: absolute;
    width: 50%;
    height: 100%;
    display: flex;
    align-items: center;
    justify-content: center;
    flex-direction: column;
    padding: 0 30px;
    text-align: center;
    top: 0;
    transform: translateX(0);
    transition: all 0.6s ease-in-out;
}

.toggle-left{
    transform: translateX(-200%);
}

.container.active .toggle-left{
    transform: translateX(0);
}

.toggle-right{
    right: 0;
    transform: translateX(0);
    width: 45%;
}

.container.active .toggle-right{
    transform: translateX(200%);
}
  </style>