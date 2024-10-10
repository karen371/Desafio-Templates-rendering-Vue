<script >
import Formulario from "./components/Formulario.vue"
export default{
    components:{
      formulario : Formulario,
    }
};
</script>

<template>
  <div class="contenedor">
    <formulario/>
  </div>

</template>

<style scoped>
  .contenedor{
    background-color: #2f4f4f;
    width: 50%;
    height: 500px;
  }
</style>
