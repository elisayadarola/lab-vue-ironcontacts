<script setup>
import contacts from "./contacts.json";
// This starter template is using Vue 3 <script setup> SFCs
// Check out https://v3.vuejs.org/api/sfc-script-setup.html#sfc-script-setup
import HelloWorld from "./components/HelloWorld.vue";

const myContacts = contacts;
console.log(myContacts);
// myContacts.splice(5)
const titulo="Iron Contacts"
</script>

<template>
  <img alt="Vue logo" src="./assets/logo.png" />
  <h1>{{titulo}}</h1>
  <div class="table">
   <td class="header">
    <th>Picture</th>
    <th>Name</th>
    <th>Popularity</th>
    <th>Won Emmy</th>
    <th>Won Oscar</th>
    </td>
  <table v-for="contact in myContacts" :key="contact">
    <tr>
    <td><img class="pics" :src="contact.pictureUrl"></td>
    <td>{{ contact.name }}</td>
    <td>{{ contact.popularity.toFixed(2) }}</td>
    <td v-if="contact.wonOscar">Gano OSCAR</td>
    <td v-else></td>
    <td v-if="contact.wonEmmy">Gano EMMY</td>
    <td v-else></td>
    
    </tr>
  </table>
  </div>

  <HelloWorld msg="Hello Vue 3 + Vite" />
</template>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
.pics {
  height: 200px;
  margin: 10px;
  align-items: center;
}
.table {
  display: flex;
 flex-direction: column; 
  align-content: center;
  border: solid pink 3px;
  justify-content:space-around;
  align-items: center;
}

.header{
  display: flex;
  flex-direction: row;
  align-content: center;
  justify-content:space-between;
  align-items: center;
}

</style>
