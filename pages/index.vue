<template>
  <div
    class="d-flex flex-column"
    style="min-height: 100vh; background-color: #ff7a00"
  >
    <div
      class="d-flex flex-column justify-content-center align-items-center text-center border-0 login-card"
      style="background-color: #eeeeee; border-radius: 50px"
    >
      <div>
        <img
          src="~/assets/logo.png"
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
        <NuxtLink to="/users" class="default-btn"> Entrar </NuxtLink>
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
    };
  },
  methods: {
    redirectToSignup() {
      if (this.email) {
        let params = this.email;
        this.$router.push({ path: "/signup", query: { email: params } });
      } else swal.fire("Preencha com seu email ;)");
    },
  },
};
</script>

<style scoped>
* {
  font-family: "Manrope";
}

.logo {
  max-width: 400px;
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
}

.default-btn {
  background-color: #c4c4c4;
  color: #111111;
  border-radius: 15px;
  border: none;
  padding: 10px 20px;
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
    max-width: 300px;
  }
  .login-card {
    min-height: 400px;
    max-width: 100%;
    padding: 0px 10px;
    margin-top: 40px;
  }
  .sub-title {
    font-size: 3.5vw;
    font-weight: bold;
  }
  .default-btn {
    max-width: 120px;
    padding: 10px;
  }
}
</style>
