<template>
  <div>
    <div class="d-flex flex-column main-container">
      <h1 style="font-weight: 600">
        Conheça os nossos Ricos em
        <span style="color: #ff7a00">Vitamina C</span>
      </h1>
      <p>
        Dentro da Technical Share você tem um cadastro fácil de uma lista de
        pessoas que podem te ajudar a tirar alguma duvida ou até mesmo para você
        conseguir melhorar o seu networking
      </p>
      <div class="users-container">
        <UserCard
          @click="userRedirect(user.id)"
          v-for="user in userList"
          :key="user.id"
          :username="user.name"
          :position="user.position"
          :techs="user.techs"
          :isMentor="user.isMentor"
          :level="user.level"
        ></UserCard>
      </div>
    </div>
  </div>
</template>

<script>
import UserCard from "~/components/UserCard.vue";
import { users } from "~/utils/mocks";

export default {
  name: "Usuários",
  components: { UserCard },
  data() {
    return {
      name: "",
      userList: users,
    };
  },
  methods: {
    userRedirect(id) {
      this.$router.push(`/users/${id}`);
    },
  },
};
</script>

<style scoped>
* {
  font-family: "Manrope";
}

.main-container {
  min-height: 100vh;
  padding: 20px;
  background-color: #f0f0f0;
}

.users-container {
  display: grid;
  grid-template-columns: auto auto;
  justify-content: space-around;
  gap: 1ch;
}

@media (max-width: 767px) {
  .main-container {
    padding: 10px 20px;
  }
  .users-container {
    display: flex;
    flex-direction: column;
  }
}
</style>
