<template>
    <div class="inputField-container">
      <!-- Renderiza el icono si se pasa como prop -->
      <div v-if="icon" class="icon">
        <font-awesome-icon :icon="icon" />
      </div>
      <!-- Campo de entrada -->
      <input
        class="inputField"
        :type="type"
        :name="name"
        :value="modelValue"
        :placeholder="placeholder"
        @input="$emit('update:modelValue', $event.target.value)"
        :required="required"
      />
    </div>
  </template>
  
  <script>
  import { defineComponent } from "vue";
  
  export default defineComponent({
    name: "InputField",
    props: {
      icon: {
        type: Object, // Se espera un objeto para usarlo con FontAwesome
        required: false,
      },
      type: {
        type: String,
        default: "text", // Tipo de input por defecto
      },
      name: {
        type: String,
        required: false,
      },
      modelValue: {
        type: String,
        default: "", // Valor inicial vacío
      },
      placeholder: {
        type: String,
        required: false,
      },
      required: {
        type: Boolean,
        default: false, // No requerido por defecto
      },
    },
    emits: ["update:modelValue"],
  });
  </script>
  
  <style scoped>
  /* Estilos específicos para el componente */
  .inputField-container {
    position: relative;
    display: flex;
    width: 100%;
    height: 50px;
  }

.inputField {
    padding: 0 20px;
    width: 100%;
    height: 100%;
    background-color: transparent;
    border: none;
    outline: none;
    border-radius: 10px;
    border: 1px solid #6c757d;
    font-size: 14px;
    color: #000;
}

.inputField[type=number]::-webkit-outer-spin-button,
.inputField[type=number]::-webkit-inner-spin-button {
    -webkit-appearance: none;
    margin: 0;
}

.inputField::placeholder {
    color: #6c757d;
  }

.icon {
    color: #000;
    position: absolute;
    right: 20px;
    top: 50%;
    transform: translateY(-50%);
    font-size: 20px;
}
  </style>