<script>
    export default{
        name:'Formulario',
        data(){
            return{
                formulario:{
                    colorFondo:'',
                    colorText:'',
                    mostrarTexto:false,
                    borde:'',
                    contenido:'',
                    tipografia:'',
                    opacidad: false,
                    size:''
                }
            };
        },
        methods: {
            emitData() {
                this.$emit('datos-actualizados', { ...this.formulario });
            }
        }
    };
</script>
<template>
    <form >
        <div class="item">
            <label for="colorFondo">Color de fondo</label>
            <input type="text" v-model="formulario.colorFondo" @input="emitData">
        </div>
        <div class="item">
            <label for="colorText">Color de Texto</label>
            <input type="text" v-model="formulario.colorText" @input="emitData">
        </div>
        <div class="item-check">
            <label for="mostrarTexto">Mostrar texto</label>
            <input type="checkbox" v-model="formulario.mostrarTexto" value="Mostrar texto" @change="emitData"/>
        </div>
        <div class="item">
            <label for="borde">Boder</label>
            <input type="range" v-model="formulario.borde" @input="emitData">
        </div>
        <div class="item">
            <label for="contenido">Contenido textual</label>
            <input type="textarea" v-model="formulario.contenido" @input="emitData">
        </div>
        <div class="item">
            <label for="tipografia">Tipografía</label>
            <select v-model="formulario.tipografia" @change="emitData">
                <option disabled value="">Seleccione una opción</option>
                <option value="Arial">Arial</option>
                <option value="Cursive">Cursive</option>
                <option value="Times New Roman">Times New Roman</option>
                <option value="Trebuchet MS">Trebuchet MS</option>
                <option value="Comic Sans MS">Comic Sans MS</option>
            </select>
            
        </div>
        <div class="item-check">
            <label for="opacidad">Opaco</label>
            <input type="checkbox" v-model="formulario.opacidad" value="Opaco" @change="emitData"/>
        </div>
        <div class="item-radio">
            <input type="radio"  value="Pequeño" v-model="formulario.size" @change="emitData">
            <label for="uno">Pequeño</label>
            <input type="radio" value="Mediano" v-model="formulario.size" @change="emitData">
            <label for="Dos">Mediano</label>
            <input type="radio"  value="Grande" v-model="formulario.size" @change="emitData">
            <label for="Dos">Grande</label>
        </div>
    </form>
</template>
<style scoped>
    form{
        color: #fff;
        width: 100%;
        margin: 20px 15px;
    }
    .item{
        display: flex;
        flex-direction: column;
        width: 100%;
        gap: 5px;
        padding-top: 10px;
    }
    .item input{
        width: 90%;
        border-radius: 10px;
        height: 30px;
    }

    .item input[type="textarea"]{
        width: 90%;
        height: 50px;
        border-radius: 10px;
    }
    select {
        appearance: none;
        width: 60%;
        height: 30px; 
        padding: 5px 10px;
        border: 1px solid #ccc;
        border-radius: 5px;
        font-size: 16px; 
        background-color: #fff; 
        color: #333; 
        box-shadow: 0 2px 5px rgba(0, 0, 0, 0.1); 
        cursor: pointer; 
    }
    select::-ms-expand {
        display: none;
    }
      
    select:focus {
        border-color: #007bff; /* Color del borde al enfocarse */
        outline: none; /* Elimina el contorno predeterminado */
        box-shadow: 0 0 5px rgba(0, 123, 255, 0.5); /* Efecto de foco */
    }
      
    .item-radio{
        display: flex;
        padding-top: 10px;
    }
</style>