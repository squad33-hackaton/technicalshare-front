<template>
  <div class="d-flex justify-content-center align-items-center" style="height: 100vh">
    <b-card class="text-center m-2 p-5 border-0" style="background-color: #eeeeee; border-radius: 50px;">
        <h1 class="mb-5">TechnicalShare</h1>
        <div class="d-flex flex-column justify-content-center">
          <NuxtLink to="/signup" class="default-btn mb-3">
              Cadastrar como mentor
          </NuxtLink>
          <NuxtLink to="/users" class="default-btn">
              Lista de mentores
          </NuxtLink>
        </div>
    </b-card>
  </div>
</template>

<script>
export default {  
  name: 'IndexPage'
}
</script>

<style scoped>
.default-btn {
 background-color: #c4c4c4;
 color: #111111;
 border-radius: 10px;
 padding: 10px 20px;
 width: 100%;
 font-size: 1.3rem;
}

.default-btn:hover {
  text-decoration: none;
}
</style>
