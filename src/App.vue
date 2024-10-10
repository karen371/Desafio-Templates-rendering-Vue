<script >
import Formulario from "./components/Formulario.vue"
import Figura from "./components/Figura.vue";
export default{
  data(){
      return{
        datos:{}
      };
    },
    components:{
      formulario: Formulario,
      figura: Figura,
    },
    methods:{
      actualizarDatos(datos){
        this.datos = {...datos};
        console.log(this.datos);
      }
    }
};
</script>

<template>
  <div class="contenedor">
    <div class="contenedor-formulario">
      <formulario @datos-actualizados="actualizarDatos"/>
    </div>
    <div class="contenedor-figura">
      <figura :datos="datos"/>
    </div>
    
  </div>
</template>

<style scoped>
  .contenedor-formulario{
    background-color: #2f4f4f;
    width: 45%;
    height: 500px;
  }
  .contenedor-figura{
    display: flex;
    justify-content: center;
    align-content: center;
    border: 2px solid #2f4f4f;
    width: 45%;
    height: 500px;
  }
  .contenedor{
      display: flex;
      justify-content: space-evenly;
  }
</style>
