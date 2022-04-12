<template>
  <div>
    <h1>{{ user.name }}</h1>
  </div>
</template>

<script>
import { users } from "~/utils/mocks";

export default {
  name: "User",
  mounted() {
    let selectedUser = users.find(
      (user) => user.id === Number(this.$route.params.id)
    );
    console.log(selectedUser);
    this.user = selectedUser;
  },
  data() {
    return {
      user: {
        name: "",
        email: "",
        isMentor: false,
        position: "",
        level: "",
        techs: "",
        links: {
          linkedin: "",
          teams: "",
          whatsapp: "",
        },
        picture: "",
      },
    };
  },
  computed: {},
};
</script>

<style scoped></style>
