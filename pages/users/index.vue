<template>
  <div>
    <div class="d-flex flex-column" style="min-height: 100vh; padding: 20px 40px; background-color: #F0F0F0;">
      <h1>Conheça os nossos Ricos em Vitamina C</h1>
      <p>Dentro da Technical Share você tem um cadastro fácil de uma lista de pessoas que podem te ajudar a tirar alguma duvida ou até mesmo para você conseguir melhorar o seu networking </p>
      <div class="users-container row">
        <UserCard @click="userRedirect(user.id)" class="col-4" v-for="user in userList" :key="user.id" :username=user.name :position=user.position></UserCard>
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
  data () {
    return {
      name: "",
      userList: users
    }
  },
  computed: {
  },
  methods: {
    userRedirect(id) {
      this.$router.push(`/users/${id}`)
    },
  }
}
</script>

<style scoped>
* {
  font-family: 'Manrope';
}

.users-container {
  display: flex;
  justify-content: space-around;
}

</style>
