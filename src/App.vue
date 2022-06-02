<template>
  <main id="app">
    <div class="m-4 text-red-500" v-for="(item, i) in countries" :key="i">
      <div class="">{{item.name}}</div>
    </div>
  </main>
</template>

<script>
import axios from "axios";
import UserComponent from "@/components/UserComponent.vue";
import gql from "graphql-tag";

export default {
  name: "App",
  apollo: {
    countries: {
      query: gql`
        {
          countries {
            name
            capital
            continent {
              code
            }
            languages {
              code
            }
          }
        }
      `,
    },
  },
  components: {
    UserComponent,
  },
  data() {
    return {
      users: [],
    };
  },
  methods: {
    /*
     * Promesas usando .then
     **/
    // listUsers() {
    //   axios
    //     .get("https://jsonplaceholder.typicode.com/users")
    //     .then((res) => (this.users = res.data))
    //     .catch((err) => console.error(err));
    // },
    /*
     * Promesas usando async/await
     **/
    async listUsers() {
      try {
        const res = await axios.get(
          "https://jsonplaceholder.typicode.com/users"
        );
        this.users = res.data;
      } catch (err) {
        console.error(err);
      }
    },
  },
  created() {
    // this.funcionDePrueba()
    this.listUsers();
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
</style>
