<template>
  <div class="container-form">
    <form class="form" @submit.prevent="handleForm">
      <h1 class="form-title">Registro de Parqueadero</h1>

      <label class="info-inputField">Nombre del Parqueadero</label>
      <InputField
        :icon="icons.pencil"
        type="text"
        name="namePark"
        v-model="values.namePark"
        placeholder="Ej: Parqueadero San Martin"
        required
      />

      <label class="info-inputField">Tarifas</label>
      <div class="inputField-double-container">
        <InputField
          :icon="icons.money"
          type="number"
          name="tarifaCarro"
          v-model="values.tarifaCarro"
          placeholder="Carro / h"
          required
        />
        <InputField
          :icon="icons.money"
          type="number"
          name="tarifaMoto"
          v-model="values.tarifaMoto"
          placeholder="Moto / h"
          required
        />
      </div>

      <label class="info-inputField">Capacidad</label>
      <div class="inputField-double-container">
        <InputField
          :icon="icons.car"
          type="number"
          name="cantidadCarros"
          v-model="values.cantidadCarros"
          placeholder="Carros"
          required
        />
        <InputField
          :icon="icons.motorcycle"
          type="number"
          name="cantidadMotos"
          v-model="values.cantidadMotos"
          placeholder="Motos"
          required
        />
      </div>

      <button type="submit" class="form-btn">Guardar</button>
    </form>
  </div>
</template>

<script>
import { defineComponent, reactive } from "vue";
import InputField from "./InputField.vue";
import { FaPencilAlt, FaMoneyCheckAlt, FaCar, FaMotorcycle, FaGift } from "oh-vue-icons/icons";

export default defineComponent({
  name: "RegisterForm",
  components: { InputField },
  setup() {
    // Estado reactivo para los datos del formulario
    const values = reactive({
      namePark: "",
      tarifaCarro: "",
      tarifaMoto: "",
      cantidadCarros: "",
      cantidadMotos: ""
    });

    const icons = {
      pencil: FaPencilAlt,
      money: FaMoneyCheckAlt,
      car: FaCar,
      motorcycle: FaMotorcycle,
      gift: FaGift,
    };

    const handleForm = () => {
      console.log(values);
    };

    return {
      values,
      icons,
      handleForm,
    };
  },
});
</script>
  
  <style scoped>
  /* Mantén tus estilos originales aquí */
  .container-form {
      width: 420px;
      background: #fff;
      padding: 5px;
      border-radius: 10px;
      align-self: center;
      margin: 0 auto;
    }
    
    .form-title {
      font-size: 25px;
      font-weight: 900;
      text-align: center;
      color: #332ff6;
    }
    
    .form {
      display: flex;
      flex-direction: column;
      gap: 5px;
      margin: 10px;
      margin-bottom: 10px;
      padding: 10px;
    }
    
    .info-inputField {
      color: #212529;
      font-weight: 500;
      font-size: 15px;
    }
    
    .inputField-double-container {
      display: flex;
      gap: 10px;
    }
    
    .form-btn {
      width: 50%;
      height: 45px;
      background-color: #332ff6;
      border: none;
      outline: none;
      border-radius: 40px;
      box-shadow: 0 0 10px rgba(0, 0, 0, .4);
      cursor: pointer;
      font-size: 15px;
      color: #fff;
      font-weight: 700;
      margin: 10px 0 0 auto;
      transition: all 0.3s ease;
    }
  
    .form-btn:hover {
      background-color: rgba(51, 47, 246, 0.9);
      transform: scale(1.01);
    }
  </style>