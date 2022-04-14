<template>
  <div>
    <div class="main-container">
      <h1 style="font-weight: 600">
        Conheça os nossos Ricos em
        <span style="color: #ff7a00">Vitamina C</span>
      </h1>
      <p>
        Dentro da Technical Share você tem um cadastro fácil de uma lista de
        pessoas que podem te ajudar a tirar alguma duvida ou até mesmo para você
        conseguir melhorar o seu networking
      </p>
      <div class="select-container">
        <el-select v-model="selectedPosition" placeholder="Selecione uma área">
          <el-option
            v-for="position in positionList"
            :key="position.value"
            :label="position.label"
            :value="position.value"
          >
          </el-option>
        </el-select>
      </div>
      <div class="users-container">
        <UserCard
          @click="userRedirect(user.id)"
          v-for="user in userList"
          :key="user.id"
          :username="user.name"
          :position="user.position"
          :techs="user.techs.split(',').join(', ')"
          :isMentor="user.isMentor"
          :level="user.level"
          v-show="selectedPosition === user.position || !selectedPosition"
        ></UserCard>
      </div>
    </div>
  </div>
</template>

<script>
import UserCard from "~/components/UserCard.vue";
import { users, positions } from "~/utils/mocks";
import { Option, Select } from "element-ui";

export default {
  name: "Usuários",
  layout: "default",
  components: {
    UserCard,
    [Select.name]: Select,
    [Option.name]: Option,
  },
  data() {
    return {
      name: "",
      userList: users,
      positionList: positions,
      selectedPosition: "",
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
  padding: 20px 40px;
  background-color: #f0f0f0;
}

.users-container {
  display: grid;
  grid-template-columns: auto auto;
  justify-content: center;
  gap: 1ch;
  margin-top: 16px;
}

.select-container {
  display: flex;
  justify-content: flex-end;
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
