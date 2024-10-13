<script>
    export default{
        props:{
            datos:{
                type:Object,
                default(){
                    return{
                        colorFondo:'',
                        colorText:'',
                        mostrarTexto:'',
                        borde:'',
                        contenido:'',
                        tipografia:'',
                        opacidad:'',
                        size:''
                    }
                },
            },
        }
    };
</script>
<template>
    <div :class="['figura', { 'transparente': datos.opacidad }]" :style="{backgroundColor: datos.colorFondo, borderRadius: datos.borde + 'px'}">
        <p v-if="datos.size === 'Pequeño'" class="pequeño" :style="{ color: datos.colorText, fontFamily: datos.tipografia}" v-show="datos.mostrarTexto"  >
            {{ datos.contenido }}
        </p>
        <p  v-else-if="datos.size === 'Mediano'" class="mediano" :style="{ color: datos.colorText, fontFamily: datos.tipografia }" v-show="datos.mostrarTexto">
            {{ datos.contenido }}
        </p>
        <p  v-else-if="datos.size === 'Grande'" class="grande" :style="{ color: datos.colorText , fontFamily: datos.tipografia }" v-show="datos.mostrarTexto">
            {{ datos.contenido }}
        </p>
        <p v-else :style="{ color: datos.colorText, fontFamily: datos.tipografia }" v-show="datos.mostrarTexto">
            {{ datos.contenido }}
        </p>
    </div>
</template>
<style scoped>
    .figura{
            display: flex;
            justify-content: center; /* Centra el contenido horizontalmente */
            align-items: center; /* Centra el contenido verticalmente */
            flex-direction: column; /* Alinea los elementos en columna */
            width: 450px; /* O el ancho que necesites */
            height: 450px; /* Ajusta según sea necesario */
            overflow: hidden; /* Oculta el desbordamiento */
            border: 1px solid #ccc; /* Para visualizar el contenedor */
            padding: 10px; /* Para agregar espacio interno */
            position: relative; /* Permite el uso de 'position: absolute' en hijos si es necesario */
    }
    .transparente{
        opacity: 0.5;
    }
    .pequeño, .mediano, .grande {
        max-width: 100%; /* Evita que el texto exceda el ancho del contenedor */
        overflow-wrap: break-word; /* Permite que las palabras se dividan si son demasiado largas */
        word-wrap: break-word; /* Para navegadores más antiguos */
    }
    
    .pequeño{
        font-size: 0.7rem;
    }
    .grande{
        font-size: 4rem;
    }
    .mediano{
        font-size: 2rem;
    }
</style>