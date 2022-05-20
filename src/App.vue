<template>
  <main id="app">
    <section class="header">
      <h1>Hola Mundo!</h1>
      <p>Esta es mi lista de cosas por hacer</p>
    </section>
    <section class="task__container">
      <div class="card">
        <h1>Pasear al perro</h1>
        <p>Tengo que sacar a blackie por que si no se aburre y tira las macetas</p>
      </div>
      <div class="card">
        <h1>Lavar el carro</h1>
        <p>Para que no llegue algun random a escribir "lavame con la ventana"</p>
      </div>
      <div class="card">
        <h1>Preparar la comida</h1>
        <p>Porque hay que seguir viviendo y el delivery esta muy caro</p>
      </div>
    </section>
  </main>
</template>

<script>


export default {
  name: 'App',

}
</script>

<style>
@import url('https://fonts.googleapis.com/css2?family=Roboto&display=swap');

#app {
  font-family: 'Roboto', sans-serif;
  /* font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px; */
}

.header{
  text-align: center;
}

.task__container {
  display: flex;

}

.card {
  border: 1px solid black;
  margin: 5px;
  padding: 8px;
  width: 33%;
}
</style>
