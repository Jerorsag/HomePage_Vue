<template>
    <div class="container-home">
      <h1 class="name-app">Name App</h1>
      <p class="slogan">¡Administra tu parqueadero fácilmente!</p>
  
      <div class="container-ventajas">
        <Ventaja title="Gestión de Espacios Inteligente" :icon="FaParking">
          Modifica la cantidad de espacios disponibles según tus necesidades y mantén el parqueadero en orden.
        </Ventaja>
  
        <Ventaja title="Control Total de Tarifas" :icon="GiTakeMyMoney">
          Ajusta las tarifas en tiempo real desde la app y optimiza tus precios según la demanda.
        </Ventaja>
  
        <Ventaja title="Cálculo Automático de Tarifas" :icon="FaCalculator">
          Nuestra app calcula el monto exacto que cada vehículo debe pagar, eliminando errores de cobro.
        </Ventaja>
  
        <Ventaja title="Monitoreo de Entradas y Salidas 24/7" :icon="FaRegularClock">
          Supervisa el flujo de vehículos al instante y asegura una administración eficiente.
        </Ventaja>
  
        <Ventaja title="Registro de Vehículos con Cámaras Inteligentes" :icon="FaCamera">
          Con tecnología de reconocimiento, registra vehículos automáticamente para mayor control y seguridad.
        </Ventaja>
      </div>
    </div>
  </template>
  
  <script>
  import { defineComponent } from "vue";
  import Ventaja from "./Ventaja.vue";
  import { FaParking, FaCalculator , FaRegularClock, FaCamera } from "oh-vue-icons/icons";
  import { GiTakeMyMoney  } from "oh-vue-icons/icons";
  
  export default defineComponent({
    name: "Home",
    components: {
      Ventaja,
    },
    data() {
      return {
        FaParking,
        FaCalculator,
        FaRegularClock,
        FaCamera,
        GiTakeMyMoney,
      };
    },
  });
  </script>
  
  <style scoped>
  /* Puedes agregar aquí los estilos específicos para este componente */

  .container-home {
    width: 50%;
    display: flex;
    flex-direction: column;
    gap: 10px;
    margin: 0 auto;
    place-items: center;
    align-self: center;
}

.name-app {
    font-size: 30px;
    font-weight: 700;
    color: #332ff6;
    text-align: center;
}

.slogan {
    font-size: 20px;
    color: #e9ecef;
}

.container-ventajas {
    display: flex;
    flex-direction: column;
    gap: 15px;
    text-align: left;
}
  </style>