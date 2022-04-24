<template>
  <h1>Login</h1>
  <form @submit.prevent="handleSubmit">
    <div class="input-container">
      <div class="input-items">
        <label>Email : </label>
        <input
          class="input"
          type="email"
          required
          v-model="email"
          placeholder="Enter your Email address"
        />
      </div>
      <div class="input-items">
        <label>Password : </label>
        <input
          type="password"
          required
          v-model="password"
          class="input"
          placeholder="Password"
        />
        <div v-if="passwordError" class="error">{{ passwordError }}</div>
      </div>
      <button>Login</button>
    </div>
  </form>
</template>

<script>
export default {
  data() {
    return {
      email: "",
      password: "",
      passwordError: "",
    };
  },
  methods: {
    handleSubmit() {
      this.passwordError =
        this.password.length > 5
          ? ""
          : "Password must be at least 6 characters long.";
      console.log("submited");
      // email = "",
      // password = "",
    },
  },
};
</script>
<style>
/* form {
  max-width: 420;
  margin: 30px auto;
  background: whitesmoke;
  text-align: left;
  padding: 40px;
  border-radius: 20px;
} */

label {
  color: rgb(38, 37, 37);
  display: inline-block;
  margin: 25px 0 5px;
  font-size: 1em;
  text-transform: uppercase;
  letter-spacing: 1px;
}
.input-container {
  display: flex;
  justify-content: center;
  align-items: center;
  flex-direction: column;
  background-color: rgb(156, 184, 236);
  margin: 100px 250px;
  padding: 50px;
  border-radius: 20px;
}
.input-items {
}
.input {
  background-color: azure;
  width: 300px;
  margin: 30px;
  height: 25px;
  display: flex;
  text-align: start;
}
button {
  padding: 10px 25px;
  border-radius: 10px;
  background-color: dodgerblue;
}
.error {
  color: rgb(53, 4, 4);
  margin: 10px 0 10px 0;
  font-size: 1em;
  font-weight: bold;
}
</style>
