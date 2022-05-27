<template>
  <main class="card">
    <div>{{ user.id }}</div>
    <div>{{ user.name }}</div>
    <div>{{ user.email }}</div>
    <div>{{ user.phone }}</div>
    <div>{{ user.address.city }}</div>
  </main>
</template>

<script>
export default {
    props: ["user"]

};
</script>

<style>
.card {
  margin: 25px;
  padding: 25px;
  background-color: rgb(255, 255, 175);
  width: 33%;
  border-radius: 15px;
  box-shadow: -3px 21px 27px -5px rgba(150, 150, 150, 0.75);
  -webkit-box-shadow: -3px 21px 27px -5px rgba(150, 150, 150, 0.75);
  -moz-box-shadow: -3px 21px 27px -5px rgba(150, 150, 150, 0.75);
}
</style>