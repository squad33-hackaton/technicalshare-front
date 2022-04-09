<template>
  <div>
    <div class="d-flex flex-column p-5" style="height: 100vh">
      <h1>Conheça os nossos Ricos em Vitamina C</h1>
      <p>Dentro da Technical Share você tem um cadastro fácil de uma lista de pessoas que podem te ajudar a tirar alguma duvida ou até mesmo para você conseguir melhorar o seu networking </p>
      <div class="users-container row">
        <UserCard class="col" v-for="user in this.users" :key="user.id" :username=user.name :position=user.id></UserCard>
        
      </div>
    </div>
  </div>
</template>

<script>
import UserCard from '~/components/UserCard.vue';
import { users } from '~/utils/mocks.js';

export default {
  components: { UserCard },
  name: 'UsersList',
  data () {
    return {
      name: "",
      users: [
      {
        id: 1,
        name: 'Murillo',
        tags: ['Frontend', 'Javascript'],
      },
      {
        id: 2,
        name: 'Celso',
        tags: ['Backend', 'PHP'],
      },
      {
        id: 3,
        name: 'Decio',
        tags: ['Fullstack', 'Javascript', 'PHP'],
      },
    ]
    }
  },
  computed: {
  }
}
</script>

<style scoped>
</style>
