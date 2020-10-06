<template>
  <div id="app">
    <forms :usersLogins="usersLogins" />
    <h3>list of available users:</h3>
    <div v-for="users in usersLogins" :key="users.login">
      <ul style="padding-left: 0">
        {{
          users.login
        }}
      </ul>
    </div>
  </div>
</template>

<script>
import forms from "./components/forms";
export default {
  name: "App",
  components: {
    forms,
  },
  data() {
    return {
      usersLogins: [
        {
          login: "shweezzy",
          passw: "1234",
        },
        {
          login: "anastasia",
          passw: "4321"
        },
        {
          login: 'peter',
          passw: "1111"
        }
      ],
    };
  },
};
</script>

<style>
</style>
