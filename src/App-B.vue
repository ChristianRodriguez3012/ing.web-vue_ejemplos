<template>
  <div id="my-component">
    <img v-if="isVisible" :src="resolvedLogoSrc" alt="Logo de Vue" width="5%" height="auto" />
    <h1 v-if="isVisible">{{ message }}</h1>
    <button v-on:click="toggleVisibility">Alternar Visibilidad</button>
    <input v-model="message">
  </div>
</template>

<script>
export default {
  name: 'MyComponent',
  data() {
    return {
      message: '',
      isVisible: true,
      logoSrc: '@/assets/logo.png',
      resolvedLogoSrc: '', // Added to resolve the logoSrc path
    };
  },
  created() {
    // Resolve the logoSrc path and store it in resolvedLogoSrc
    this.resolvedLogoSrc = require('@/assets/logo.png');
    console.log('Resolved Logo Src:', this.resolvedLogoSrc);
  },
  methods: {
    toggleVisibility() {
      this.isVisible = !this.isVisible;
    },
    sayHello() {
      alert('Hola');
    }
  }
};
</script>

<style scoped>
/* Styles for centering the content */
#my-component {
  display: flex;
  flex-direction: column;
  align-items: center;
  justify-content: center;
  height: 100vh;
}

/* Styles for the logo */
img {
  width: 5%;
  height: auto; /* Mantiene la proporción original */
}

/* Styles for the heading */
h1 {
  font-size: 24px; /* Ajusta el tamaño de la fuente como desees */
  margin-bottom: 20px; /* Añade margen inferior al encabezado */
}

/* Styles for the button */
button {
  padding: 10px 20px;
  border: 1px solid #ccc;
  border-radius: 4px;
  cursor: pointer;
}

/* Styles for the input field */
input {
  padding: 10px;
  border: 1px solid #ccc;
  border-radius: 4px;
  width: 300px; /* Ajusta el ancho como sea necesario */
}
</style>
