<template>
  <div id="my-component">
    <img v-if="isVisible" :src="logoSrc" alt="Logo de Vue" width="5%" height="auto" />
    <p v-text="message">HOLA MUNDO DESDE VUE</p>
    <button v-on:click="event => isVisible = !isVisible">Alternar Visibilidad</button>
    <ul>
      <li v-for="item in list" :key="item.id">{{ item.text }}</li>
    </ul>
    <input type="text" v-model="message" />
  </div>
</template>

<script>
import logoSrc from "@/assets/logo.png"; // Ejemplo de importación

export default {
  name: 'App',
  data() {
    return {
      message: '¡Hola Mundo con Vue!',
      isVisible: true,
      logoSrc,
      list: [
        { id: 1, text: 'First item' },
        { id: 2, text: 'Second item' },
        { id: 3, text: 'Third item' },
        { id: 4, text: 'Fourth item' },
      ],
    };
  },
};
</script>

<style scoped>
/* Estilos para centrar el contenido */
#my-component {
  display: flex;
  flex-direction: column;
  align-items: center;
  justify-content: center;
  height: 100vh;
}

/* Estilos para el logo */
img {
  width: 5%;
  height: auto; /* Mantiene la proporción original */
}

/* Estilos para el botón (posicionado en la parte inferior y centrado) */
button {
  position: absolute;
  bottom: 20px;
  left: 50%;
  transform: translate(-50%, 0);
}

/* Estilos para el texto debajo del logo */
p {
  text-align: center;
  font-size: 16px;
  margin-top: 10px;
}

/* Estilos para la lista */
ul {
  list-style: none; /* Elimina los puntos de bala predeterminados */
  padding: 0; /* Restablece el relleno predeterminado */
  margin: 20px 0; /* Añade margen superior e inferior */
}

/* Estilos para los elementos de la lista (li) */
li {
  padding: 10px;
  border-bottom: 1px solid #ccc;
  margin-bottom: 5px;
}

/* Estilos para el textbox */
input[type="text"] {
  width: 200px; /* Ajusta el ancho según sea necesario */
  padding: 10px;
  border: 1px solid #ccc;
  margin-top: 10px;
}
</style>
