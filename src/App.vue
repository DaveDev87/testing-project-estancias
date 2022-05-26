<template>
  <main id="app">
    <section class="header">
      <h1>{{ title }}</h1>
      <p>{{ subtitle }}</p>
    </section>
    <section>
      <div class="card">
        <div>Nombre: {{ user.name }}</div>
        <div>Edad: {{ user.age }}</div>
        <span class="puede_pasar" v-if="user.age >= 18">Pasele!</span>
        <span class="no_puede_pasar" v-else>No pasa</span>
      </div>
    </section>
    <!-- <section class="task__container">
      <div v-for="(task, index) in tasks" :key="index">
        <div v-if="task.completed === false" class="card">
          <div class="task__date">{{ task.date }}</div>
          <h1>{{ task.title }}</h1>
          <span>{{ task.author }}</span>
          <p>{{ task.description }}</p>
        </div>
      </div>
    </section> -->
  </main>
</template>

<script>
export default {
  name: "App",
  // mounted() {
  //   const body = {
  //     email: "alexruedarivas@gmail.com",
  //     user: "David A. Rueda",
  //     sendEmailToUser: true,
  //   };

  //   fetch(
  //     "https://4519cjvuci.execute-api.us-east-1.amazonaws.com/prod/convocatoria-evaluador/emailalert",
  //     {
  //       method: "POST",
  //       body: JSON.stringify(body),
  //       headers: new Headers({
  //         "Content-Type": "application/json",
  //         "Access-Control-Allow-Origin:": "*"
  //       }),
  //     }
  //   )
  //     .then((res) => res.json())
  //     .then((res) => console.log(res))
  //     .catch((err) => console.log("unu", err));
  // },
  data() {
    return {
      title: "Hola amigos",
      subtitle: "Lista de cosas para hacer:",

      user: {
        name: "Pepe",
        age: 20,
        active: true,
      },

      // tasks: [
      //   {
      //     title: "Lavar la ropa",
      //     description: "Para no oler mal",
      //     author: "David",
      //     date: "2022-05-1",
      //     completed: true,
      //   },
      //   {
      //     title: "lavar los platos",
      //     description: "Para no enfermarse",
      //     date: "2022-05-1",
      //     author: "Sherlyn",
      //     completed: true,
      //   },
      //   {
      //     title: "Hacer la tarea",
      //     description: "Porque si no me reprueba Joel",
      //     date: "2022-05-1",
      //     author: "Cris",
      //     completed: false,
      //   },
      // ],
    };
  },
};
</script>

<style>
@import url("https://fonts.googleapis.com/css2?family=Roboto&display=swap");

#app {
  font-family: "Roboto", sans-serif;
  /* font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px; */
}

.header {
  text-align: center;
}

.task__container {
  display: flex;
  flex-wrap: wrap;
}

.task__date {
  text-align: right;
}

.puede_pasar {
  color: green;
}

.no_puede_pasar {
  color: red;
}

.card {
  border: 1px solid black;
  margin: 5px;
  padding: 8px;
  width: 33%;
}
</style>
