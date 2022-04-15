<template>
  <div>
    <div class="main-container">
      <div class="text-container">
        <h1 style="font-weight: 600">
          Conheça os nossos Ricos em
          <span style="color: #ff7a00">Vitamina C</span>
        </h1>
        <p>
          Dentro da Technical Share você tem um cadastro fácil de uma lista de
          pessoas que podem te ajudar a tirar alguma dúvida ou até mesmo para
          você conseguir melhorar o seu networking.
        </p>
      </div>
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
      <div class="users-container" v-if="!loading">
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
      <div v-else class="loader"></div>
    </div>
  </div>
</template>

<script>
import UserCard from "~/components/UserCard.vue";
import { users, positions } from "~/utils/mocks";
import { Option, Select } from "element-ui";

export default {
  async beforeMount() {
    try {
      this.loading = true;
      let url = "//api.localhost";
      let response = await this.$axios.$get(url + "/users");
      this.userList = response;
      this.loading = false;
    } catch (e) {
      this.loading = false;
      console.log(e);
    }
  },
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
      userList: [],
      positionList: positions,
      selectedPosition: "",
      loading: false,
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
  background-image: url("~/assets/default-bg.png");
  background-repeat: no-repeat;
  background-size: cover;
  background-position: center;
}

.text-container {
  margin-top: 60px;
}

.users-container {
  display: grid;
  grid-template-columns: 1fr 1fr 1fr;
  gap: 1ch;
  margin-top: 16px;
}

.select-container {
  display: flex;
  justify-content: flex-end;
}

.loader {
  border: 16px solid #f3f3f3;
  border-top: 16px solid #fe5517;
  border-radius: 50%;
  width: 120px;
  height: 120px;
  animation: spin 2s linear infinite;
}

@keyframes spin {
  0% {
    transform: rotate(0deg);
  }
  100% {
    transform: rotate(360deg);
  }
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
