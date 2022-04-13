<template>
  <div>
    <!-- TODO -> transformar UserDetails em componente -->
    <div
      class="d-flex flex-column align-items-center"
      style="background-color: #f0f0f0; min-height: 100vh"
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
              <small>{{ user.techs }}</small>
            </p>
            <p class="mb-1">Conecte-se com {{ user.name }}</p>
            <div
              class="user-details-links d-flex align-items-center mb-3"
              style="gap: 3ch"
            >
              <a target="_blank" :href="this.user.links.linkedin">
                <font-awesome-icon
                  icon="fab fa-linkedin"
                  style="font-size: 32px"
              /></a>
              <a target="_blank" :href="this.user.links.teams">
                <img
                  src="~/assets/teams.svg"
                  alt="Logo do Microsoft Teams"
                  height="28px"
                  width="28px"
                />
              </a>
              <a target="_blank" :href="this.user.links.whatsapp">
                <font-awesome-icon
                  icon="fab fa-whatsapp"
                  style="font-size: 32px"
                />
              </a>
            </div>
          </div>
        </div>
        <form>
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
import swal from "sweetalert2";
import { users } from "~/utils/mocks";

export default {
  name: "User",
  layout: "default",
  beforeMount() {
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
  computed: {},
};
</script>

<style scoped>
* {
  font-family: "Manrope";
}

.user-details {
  background-color: #fff;
  box-shadow: 4px 8px 11px -6px rgba(0, 0, 0, 0.25);
  border-radius: 20px;
  padding: 20px 40px;
  margin-top: 20px;
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
  }

  .user-details-title {
    font-size: 16px;
  }

  .user-details-subtext {
    font-size: 14px;
  }
}
</style>
