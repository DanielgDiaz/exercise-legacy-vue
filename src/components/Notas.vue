<template>
  <div id="componente">
    <h1>Notas</h1>
    <h1>Resultado académico</h1>
        <label for="name"></label>Introduzca su nombre
    <input
      type="name"
      v-model="name"
      name="name"
      id="name"
      placeholder="Indique su nombre"
    />
        <label for="materia"></label>Introduzca su materia
    <input
      type="name"
      v-model="materia"
      name="materia"
      id="materia"
      placeholder="Indique su materia"
    />
    <label for="nota"></label>Introduzca su nota
    <input
      type="number"
      v-model="nota"
      name="nota"
      id="nota"
      placeholder="Indique su nota"
    />
    <button @click="calificacion">Enviar</button>
    <div id="res">
      <h2>{{ name }}</h2>
      <div>
        
      {{materia}}
      {{ message }}
      </div>
    </div>
  </div>
  
</template>
<script>
export default {
  name: "Notas",
  data: () => ({
    materia: "",
    nota: "",
    message: "",
  }),
  methods: {
    calificacion() {
      console.log("hola");
      let nota = this.nota;

      if (nota < 3 && nota >= 0) {
        this.message = "Muy deficiente";
      }
      if (nota >= 3 && nota < 5) {
        this.message = "Inuficiente";
      }
      if (nota < 6 && nota >= 5) {
        this.message = "Suficiente";
      }
      if (nota >= 6 && nota < 7) {
        this.message = "Bien";
      }
      if (nota >= 7 && nota < 9) {
        this.message = "Notable";
      }
      if (nota >= 9) {
        this.message = "Sobresaliente";
      }
    },
  },
};
</script>
