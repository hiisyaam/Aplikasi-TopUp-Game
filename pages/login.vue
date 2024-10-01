<template>
  <div class="login-container d-flex align-items-center justify-content-center">
    <div class="login-box text-center">
      <!-- Logo Game -->
      <img src="/static/favicon.ico" alt="Game Logo" class="game-logo mb-4" />

      <!-- Form -->
      <b-form @submit="onSubmit" @reset="onReset" v-if="show">
        <b-form-group
          id="input-group-email"
          label="Email Address:"
          label-for="input-email"
        >
          <b-form-input
            id="input-email"
            v-model="form.email"
            type="email"
            placeholder="Enter email"
            required
          ></b-form-input>
        </b-form-group>

        <b-form-group
          id="input-group-password"
          label="Password:"
          label-for="input-password"
        >
          <b-form-input
            id="input-password"
            v-model="form.password"
            type="password"
            placeholder="Enter password"
            required
          ></b-form-input>
        </b-form-group>

        <b-button type="submit" variant="primary" class="w-100">Login</b-button>
      </b-form>
    </div>
  </div>
</template>
<style>
.login-container {
  height: 100vh; /* Buat tinggi halaman penuh */
  background-color: #f0f0f0; /* Warna latar belakang halaman */
}

.login-box {
  width: 100%;
  max-width: 400px; /* Ukuran maksimal form */
  padding: 2rem;
  background-color: white;
  border-radius: 8px;
  box-shadow: 0 0 15px rgba(0, 0, 0, 0.1);
}

.game-logo {
  width: 150px; /* Ukuran logo game */
}

@media (max-width: 576px) {
  .login-box {
    padding: 1.5rem;
  }
}
</style>

<script>
export default {
  data() {
    return {
      form: {
        email: "",
        password: "",
      },
      show: true,
    };
  },
  methods: {
    onSubmit(event) {
      event.preventDefault();
      alert(`Email: ${this.form.email}\nPassword: ${this.form.password}`);
    },
    onReset(event) {
      event.preventDefault();
      this.form.email = "";
      this.form.password = "";
    },
  },
};
</script>
