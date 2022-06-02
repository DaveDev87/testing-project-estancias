<template>
  <main id="app">
    <div class="card" v-for="(item, i) in countries" :key="i">
      <h1>Country</h1>
      <div class="">{{item.name}}</div>
      <div class="">{{item.currency}}</div>
      <div v-for="(language, i) in item.languages" :key="i">
        <span>{{language.code}}</span>
      </div>
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
            currency
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

.card {
  margin: 25px;
  padding: 25px;
  background-color: rgb(243, 212, 250);
  width: 33%;
  border-radius: 15px;
  box-shadow: -3px 21px 27px -5px rgba(150, 150, 150, 0.75);
  -webkit-box-shadow: -3px 21px 27px -5px rgba(150, 150, 150, 0.75);
  -moz-box-shadow: -3px 21px 27px -5px rgba(150, 150, 150, 0.75);
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
