<template>
    <div class="ventaja">
      <div v-if="icon" >
        <v-icon :icon="icon" class="ventaja-icon" />
      </div>
      <div class="ventaja-container-info">
        <span class="ventaja-title">{{ title }}</span>
        <p class="ventaja-info">
          <slot></slot>
        </p>
      </div>
    </div>
  </template>
  
  <script>
  import { defineComponent } from "vue";
  
  export default defineComponent({
    name: "Ventaja",
    props: {
      title: {
        type: String,
        required: true,
      },
      icon: {
        type: Object, // En Vue con FontAwesome, los íconos se pasan como objetos
        required: false,
      },
    },
  });
  </script>
  
  <style scoped>
  /* Puedes mantener los mismos estilos de tu archivo CSS */
  .ventaja {
    display: flex;
    align-items: center;
    gap: 30px;
    color: #e9ecef;
}

.ventaja-icon {
    font-size: 50px;
    width: 10%;
}

.ventaja-container-info {
    display: flex;
    flex-direction: column;
    width: 90%;
}

.ventaja-title {
    font-size: 18px;
    font-weight: 700;
}

.ventaja-info {
    font-size: 15px;
}
  </style>