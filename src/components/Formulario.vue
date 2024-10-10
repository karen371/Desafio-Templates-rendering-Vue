<script>
    export default{
        return:{
            colorFondo:'',
            colorText:'',
            mostrarTexto:'',
            borde:'',
            contenido:'',
            tipografia:'',
            opacidad:'',
            size:''
        }
    };
</script>
<template>
    <form >
        <div class="item">
            <label for="colorFondo">Color de fondo</label>
            <input type="text" v-model="colorFondo">
        </div>
        <div class="item">
            <label for="colorText">Color de fondo</label>
            <input type="text" v-model="colorText">
        </div>
        <div class="item-check">
            <label for="mostrarTexto">Mostrar texto</label>
            <input type="checkbox" v-model="mostrarTexto" value="Mostrar texto"/>
        </div>
        <div class="item">
            <label for="borde">Boder</label>
            <input type="range" v-model="borde">
        </div>
        <div class="item">
            <label for="contenido">Contenido textual</label>
            <input type="textarea" v-model="contenido">
        </div>
        <div class="item">
            <label for="tipografia">Tipografía</label>
            <select v-model="tipografia">
                <option desabled value="">Selecione una opcion</option>
                <option value="normal">Normal</option>
                <option value="italic">Cursiva</option>
                <option value="oblique">Oblicua</option>
            </select>
        </div>
        <div class="item-check">
            <label for="opacidad">Opaco</label>
            <input type="checkbox" v-model="opacidad" value="Opaco"/>
        </div>
        <div class="item-radio">
            <input type="radio"  value="Pequeño" v-model="size">
            <label for="uno">Pequeño</label>
            <input type="radio" value="Mediano" v-model="size">
            <label for="Dos">Mediano</label>
            <input type="radio"  value="Grande" v-model="size">
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
    .item select {
        appearance: none;
        width: 60%;
        height: 30px; /* Altura deseada */
        line-height: 50px; /* Alineación vertical del texto */
        padding: 0 10px; /* Asegura un buen espaciado interno */
        border: 1px solid #ccc; /* Borde opcional */
        border-radius: 5px; /* Bordes redondeados opcionales */
    }
    .item-radio{
        display: flex;
        padding-top: 10px;
    }
</style>