<template>
  <div class="d-flex justify-content-center align-items-center" style="min-height: 100vh; background-color: #FF7A00">
    <div class="d-flex flex-column justify-content-center align-items-center text-center border-0 login-card" style="background-color: #eeeeee; border-radius: 50px;">
        <div>
        <img src="~/assets/logo.png" class="logo" alt="Logo da TechnicalShare">
        <p class="sub-title">Apresentando pessoas e facilitando conexões</p>
        </div>
        <div class="form-group">
          <label for="email" class="form-title" style="color: #8C8C8C;">Entre com o seu email da FCamara</label>
          <input type="email" class="form-control" id="email" v-model="email">
        </div>
        <div class="d-flex align-items-center" style="gap: 1ch;">
          <button @click="redirectToSignup" class="default-btn" style="background-color: #36357E; color: #fff;">
              Criar perfil
          </button>
          <NuxtLink to="/users" class="default-btn">
              Entrar
          </NuxtLink>
        </div>
    </div>
  </div>
</template>

<script>
import swal from 'sweetalert2';

export default {  
  name: 'Login',
  data() {
    return {
      email: ""
    }
  },
  methods: {
    redirectToSignup() {
      if (this.email) {
        let params = this.email
        this.$router.push({ path: '/signup', query: { email: params } })
      } else swal.fire('Preencha com seu email ;)')
    }
  }
}
</script>

<style scoped>
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
  margin: 60px;
}

.default-btn {
 background-color: #c4c4c4;
 color: #111111;
 border-radius: 15px;
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

  @media (max-width: 575px) {
    .logo {
      max-width: 300px;
    }
    .login-card {
      min-height: 400px;
      max-width: 100%;
    }
    .sub-title {
      font-size: 5vw;
    }
    .default-btn {
      width: 120px;
    }
  }
</style>
