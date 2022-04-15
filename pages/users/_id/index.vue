<template>
  <div>
    <!-- TODO -> transformar UserDetails em componente -->
    <div
      class="d-flex flex-column align-items-center justify-content-center main-container"
      style="min-height: 100vh"
    >
      <div class="user-details">
        <div class="user-details-content">
          <div>
            <font-awesome-icon
              icon="fa-solid fa-user"
              style="font-size: 3rem"
            />
          </div>
          <div>
            <p class="user-details-tag mb-0" v-if="user.isMentor">Mentor</p>
            <p class="user-details-title mb-0">{{ user.name }}</p>
            <p class="user-details-subtext">
              {{ user.position }} {{ user.level }}
            </p>
            <p class="user-details-techs">
              Ferramentas que mais utiliza: <br />

              <b>{{ user.techs.split(";").join(", ") }}</b>
            </p>
            <p
              v-if="
                user.links.linkedin || user.links.whatsapp || user.links.teams
              "
              class="mb-1"
            >
              Conecte-se com {{ user.name }}
            </p>
            <div
              class="user-details-links d-flex align-items-center mb-3"
              style="gap: 3ch"
            >
              <a
                target="_blank"
                :href="this.user.links.linkedin"
                v-if="user.links.linkedin"
              >
                <img
                  src="~/assets/linkedin.svg"
                  alt="Logo do Linkedin"
                  height="28px"
                  width="28px"
              /></a>
              <a
                target="_blank"
                :href="this.user.links.teams"
                v-if="user.links.teams"
              >
                <img
                  src="~/assets/teams.svg"
                  alt="Logo do Microsoft Teams"
                  height="28px"
                  width="28px"
                />
              </a>
              <a
                target="_blank"
                :href="whatsappRedirect"
                v-if="user.links.whatsapp"
              >
                <img
                  src="~/assets/whatsapp.svg"
                  alt="Logo do Whatsapp"
                  height="28px"
                  width="28px"
                />
              </a>
            </div>
          </div>
        </div>
        <form v-if="user.isMentor">
          <div class="form-group d-flex flex-column">
            <label for="userMessage"
              >Tire suas dúvidas com {{ user.name }}</label
            >
            <textarea
              class="form-control"
              v-model="message"
              id="userMessage"
              rows="3"
              style="resize: none"
              required
              aria-describedby="helpBlock"
            ></textarea>
            <small id="helpBlock" class="form-text text-muted"
              ><i
                >Você será redirecionado para seu serviço de email para enviar
                sua dúvida ;)</i
              ></small
            >
          </div>
          <button @click="submitMessage" class="form-btn mb-3">Enviar</button>
        </form>
      </div>
    </div>
  </div>
</template>

<script>
import { users } from "~/utils/mocks";

export default {
  async beforeMount() {
    try {
      let url = "//api.localhost";
      let response = await this.$axios.$get(
        url + `/users/${this.$route.params.id}`
      );
      this.user = response;
    } catch (e) {
      console.log(e);
    }
  },
  name: "User",
  layout: "default",
  // beforeMount() {
  //   let selectedUser = users.find(
  //     (user) => user.id === Number(this.$route.params.id)
  //   );
  //   console.log(selectedUser);
  //   this.user = selectedUser;
  // },
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
      message: "",
    };
  },
  methods: {
    submitMessage() {
      if (this.message) {
        //TODO -> Inserir uma mensagem de envio de email com o sweetalert.
        window.open(
          `mailto:${this.user.email}?subject=TechnicalShare - Alguém te enviou uma mensagem!&body=${this.message}`
        );
      }
    },
  },
  computed: {
    whatsappRedirect() {
      return "//wa.me/" + this.user.links.whatsapp;
    },
  },
};
</script>

<style scoped>
* {
  font-family: "Manrope";
}

.main-container {
  background-image: url("~/assets/default-bg.png");
  background-repeat: no-repeat;
  background-size: cover;
  background-position: center;
}

.user-details {
  background-color: #fff;
  box-shadow: 4px 8px 11px -6px rgba(0, 0, 0, 0.25);
  border-radius: 20px;
  padding: 20px 40px;
  margin-top: 20px;
  min-width: 500px;
}

.user-details-content {
  display: flex;
  align-items: flex-start;
  gap: 1ch;
}

.form-btn {
  background: #5251a2;
  border-radius: 15px;
  padding: 10px 20px;
  border: 0;
  font-size: 14px;
  font-weight: bold;
  color: #ffffff;
}
.user-details-title {
  font-size: 1.5rem;
  font-weight: bold;
}

.user-details-subtext {
  font-size: 1.2rem;
  color: #ff7a00;
  font-weight: bold;
}

.user-details-tag {
  font-size: 12px;
  font-weight: bold;
  padding: 2.5px 5px;
  background-color: #ff7a00;
  border-radius: 20px;
  text-align: center;
  max-width: 65px;
}

.form-control {
  border-radius: 20px;
}

@media (max-width: 767px) {
  .user-details {
    padding: 20px;
    width: auto;
    margin: 10px;
    min-width: auto;
  }

  .user-details-title {
    font-size: 16px;
  }

  .user-details-subtext {
    font-size: 14px;
  }
}
</style>
