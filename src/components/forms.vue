<template>
  <div class="labelsContainer">
    <div>
      <label>
        Login
        <input class="loginInput" type="text" v-model="login" />
      </label>
    </div>
    <br />
    <div>
      <label>
        Password
        <input type="text" v-model="password" />
      </label>
    </div>
    <br />
    <button @click="onLogin" style="float: right">try it</button>
    <div v-if="isAuthorized === true" class="succes-auth">
      {{ this.login }} welcome back
    </div>
    <div v-if="isAuthorized === false" class="failed-auth">
      Login or pass is wrong!!!
    </div>
  </div>
</template>

<script>
export default {
  name: "forms",
  props: {
    usersLogins: {
      type: Array,
      default: () => [],
    },
  },
  data() {
    return {
      login: null,
      password: null,
      isAuthorized: null,
    };
  },
  methods: {
    onLogin() {
      const newUser = this.usersLogins.find(
        (item) => item.login === this.login && item.passw === this.password
      );
      this.isAuthorized = !!newUser;
    },
  },
};
</script>

<style scoped>
.failed-auth {
  color: red;
}
.succes-auth {
  color: green;
}
.labelsContainer {
  width: 350px;
  margin-left: 45%;
}
.loginInput {
  margin-left: 9.7%;
}
input {
  width: 72%;
  margin-left: 3%;
}
button {
  width: 20%;
  height: 2em;
  border: none;
}
</style>
