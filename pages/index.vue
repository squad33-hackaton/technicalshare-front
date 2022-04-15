<template>
  <div
    class="d-flex flex-column justify-content-center main-container"
    style="min-height: 100vh"
  >
    <div
      class="d-flex flex-column justify-content-center align-items-center text-center border-0 login-card"
      style="background-color: #eeeeee; border-radius: 50px"
    >
      <div>
        <img
          src="~/assets/logo.svg"
          class="logo"
          alt="Logo da TechnicalShare"
        />
        <p class="sub-title">Apresentando pessoas e facilitando conexões</p>
      </div>
      <div class="form-group">
        <label for="email" class="form-title" style="color: #8c8c8c"
          >Entre com o seu email da FCamara</label
        >
        <input type="email" class="form-control" id="email" v-model="email" />
      </div>
      <div class="d-flex align-items-center" style="gap: 1ch">
        <button
          @click="redirectToSignup"
          class="default-btn"
          style="background-color: #36357e; color: #fff"
        >
          Criar perfil
        </button>
        <button @click="redirectToUsers" class="default-btn">Entrar</button>
      </div>
    </div>
  </div>
</template>

<script>
import swal from "sweetalert2";

export default {
  name: "Login",
  layout: "login",
  data() {
    return {
      email: "",
      loading: false,
    };
  },
  methods: {
    async redirectToSignup() {
      this.loading = true;
      if (!this.email) {
        swal.fire("Preencha com seu email ;)");
        this.loading = false;
        return;
      }
      let url = "//api.localhost";
      let response = await this.$axios.$get(url + `/users?email=${this.email}`);
      if (response) {
        swal.fire("Email já cadastrado! Utilize o botão de login.");
        this.loading = false;
        return;
      } else if (this.email && !response) {
        let params = this.email;
        this.loading = false;
        this.$router.push({ path: "/signup", query: { email: params } });
      }
    },
    async redirectToUsers() {
      this.loading = true;
      if (!this.email) {
        swal.fire("Preencha com seu email ;)");
        this.loading = false;
        return;
      }
      let url = "//api.localhost";
      let response = await this.$axios.$get(url + `/users?email=${this.email}`);
      if (!response) {
        swal.fire('Email não encontrado. Utilize o botão de "Criar perfil"');
        this.loading = false;
        return;
      } else if (this.email && response) {
        this.loading = false;
        this.$router.push({ path: "/users" });
      }
    },
  },
};
</script>

<style scoped>
* {
  font-family: "Manrope";
}

.main-container {
  background-image: url("~/assets/login-bg.png");
  background-repeat: no-repeat;
  background-size: cover;
  background-position: center;
}

.logo {
  min-width: 420px;
}

.sub-title {
  font-size: 1.6rem;
  font-weight: 300;
}

.login-card {
  padding: 20px 40px;
  min-height: 520px;
  gap: 1ch;
  margin: 20px auto;
  box-shadow: rgba(99, 99, 99, 0.2) 0px 2px 8px 0px;
}

.default-btn {
  background-color: #c4c4c4;
  color: #111111;
  border-radius: 15px;
  border: none;
  padding: 10px;
  width: 100%;
  font-size: 1.1rem;
  min-width: 150px;
  max-width: 300px;
  font-weight: 500;
}

.default-btn:hover {
  text-decoration: none;
}

@media (max-width: 640px) {
  .logo {
    min-width: 280px;
  }
  .login-card {
    min-height: 400px;
    max-width: 100%;
    padding: 0px 10px;
    margin: 40px 10px 10px 10px;
  }
  .sub-title {
    font-size: 3.5vw;
    font-weight: bold;
  }
  .default-btn {
    min-width: 100px;
    max-width: 120px;
    padding: 5px;
    font-size: 3.5vw;
  }
}
</style>
