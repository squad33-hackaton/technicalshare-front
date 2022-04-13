<template>
  <div>
    <div class="header-container">
      <NuxtLink to="./">
        <font-awesome-icon icon="fas fa-arrow-circle-left" class="back-arrow" />
      </NuxtLink>
      <p class="page-title mb-0">{{ getRouteName }}</p>
      <div><!--  --></div>
    </div>
    <Nuxt />
  </div>
</template>

<script>
export default {
  name: "default",
  computed: {
    getRouteName() {
      if (this.$route.name === "users-id") return "Perfil";
      if (this.$route.name === "users") return "Usuários";
      if (this.$route.name === "signup") return "Cadastro";
      else return "";
    },
  },
};
</script>

<style scoped>
.header-container {
  background-color: #f0f0f0;
  padding: 20px;
  top: 0px;
  display: flex;
  justify-content: space-between;
}
.back-arrow {
  color: #5251a2;
  font-size: 32px;
}

.page-title {
  font-size: 24px;
  font-weight: bold;
}

@media (max-width: 767px) {
  .header-container {
    padding: 10px;
    top: 0px;
  }
  .back-arrow {
    font-size: 24px;
  }
  .page-title {
    font-size: 16px;
    font-weight: bold;
  }
}
</style>
