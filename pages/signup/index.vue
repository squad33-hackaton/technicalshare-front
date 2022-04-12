<template>
  <div
    class="d-flex flex-column justify-content-center align-items-center"
    style="min-height: 100vh; background-color: #f0f0f0"
  >
    <form>
      <div class="form-group">
        <label for="name" class="form-title"
          >Qual o seu nome? <small>*</small></label
        >
        <input
          required
          type="text"
          class="form-control"
          id="name"
          v-model="name"
        />
      </div>
      <div class="form-group">
        <label for="position" class="form-title"
          >Com o que você trabalha? <small>*</small></label
        ><br />
        <div
          class="form-check form-check-inline mb-2 position-input"
          id="position-1"
          @click="selectPosition('position-1')"
        >
          <input
            class="form-check-input"
            type="radio"
            id="frontend"
            value="Front-end"
            v-model="position"
            required
          />
          <label class="form-check-label" for="frontend">Front-end</label>
        </div>
        <div
          class="form-check form-check-inline mb-2 position-input"
          id="position-2"
          @click="selectPosition('position-2')"
        >
          <input
            class="form-check-input"
            type="radio"
            id="backend"
            value="Back-end"
            v-model="position"
            required
          />
          <label class="form-check-label" for="backend">Back-end</label>
        </div>
        <div
          class="form-check form-check-inline mb-2 position-input"
          id="position-3"
          @click="selectPosition('position-3')"
        >
          <input
            class="form-check-input"
            type="radio"
            id="fullstack"
            value="Full Stack"
            v-model="position"
            required
          />
          <label class="form-check-label" for="fullstack">Full Stack</label>
        </div>
        <div
          class="form-check form-check-inline mb-2 position-input"
          id="position-4"
          @click="selectPosition('position-4')"
        >
          <input
            class="form-check-input"
            type="radio"
            id="ux"
            value="UX Design"
            v-model="position"
            required
          />
          <label class="form-check-label" for="ux">UX Design</label>
        </div>
        <div
          class="form-check form-check-inline mb-2 position-input"
          id="position-5"
          @click="selectPosition('position-5')"
        >
          <input
            class="form-check-input"
            type="radio"
            id="ui"
            value="UI Design"
            v-model="position"
            required
          />
          <label class="form-check-label" for="ui">UI Design</label>
        </div>
        <div
          class="form-check form-check-inline mb-2 position-input"
          id="position-6"
          @click="selectPosition('position-6')"
        >
          <input
            class="form-check-input"
            type="radio"
            id="ux/ui"
            value="UX/UI Design"
            v-model="position"
            required
          />
          <label class="form-check-label" for="ux/ui">UX/UI Design</label>
        </div>
      </div>
      <div class="form-group">
        <label for="name" class="form-title"
          >Qual o seu nível de senioridade? <small>*</small></label
        ><br />
        <div
          class="form-check form-check-inline mb-2 level-input"
          id="level-1"
          @click="selectLevel('level-1')"
        >
          <input
            class="form-check-input"
            type="radio"
            id="trainee"
            value="Trainee"
            v-model="level"
            required
          />
          <label class="form-check-label" for="trainee">Trainee</label>
        </div>
        <div
          class="form-check form-check-inline mb-2 level-input"
          id="level-2"
          @click="selectLevel('level-2')"
        >
          <input
            class="form-check-input"
            type="radio"
            id="junior"
            value="Júnior"
            v-model="level"
            required
          />
          <label class="form-check-label" for="junior">Júnior</label>
        </div>
        <div
          class="form-check form-check-inline mb-2 level-input"
          id="level-3"
          @click="selectLevel('level-3')"
        >
          <input
            class="form-check-input"
            type="radio"
            id="pleno"
            value="Pleno"
            v-model="level"
            required
          />
          <label class="form-check-label" for="pleno">Pleno</label>
        </div>
        <div
          class="form-check form-check-inline mb-2 level-input"
          id="level-4"
          @click="selectLevel('level-4')"
        >
          <input
            class="form-check-input"
            type="radio"
            id="senior"
            value="Sênior"
            v-model="level"
            required
          />
          <label class="form-check-label" for="senior">Sênior</label>
        </div>
      </div>
      <div class="form-group">
        <label for="name" class="form-title"
          >Você se dispõe a ser mentor? <small>*</small></label
        ><br />
        <div
          class="form-check form-check-inline mb-2 mentor-input"
          id="mentor-1"
          @click="selectMentor('mentor-1')"
        >
          <input
            class="form-check-input"
            type="radio"
            id="yes"
            :value="true"
            v-model="isMentor"
            required
          />
          <label class="form-check-label" for="yes">Sim</label>
        </div>
        <div
          class="form-check form-check-inline mb-2 mentor-input"
          id="mentor-2"
          @click="selectMentor('mentor-2')"
        >
          <input
            class="form-check-input"
            type="radio"
            id="no"
            :value="false"
            v-model="isMentor"
            required
          />
          <label class="form-check-label" for="no">Não</label>
        </div>
      </div>
      <div class="form-group">
        <label for="tech" class="form-title mb-0"
          >Quais ferramentas você domina? <small>*</small></label
        >
        <input
          type="text"
          class="form-control"
          id="tech"
          v-model="techs"
          placeholder="Utilize apenas vírgulas (sem espaços) para separar as ferramentas."
          required
        />
      </div>
      <div class="form-group">
        <label class="form-title">Links para você se conectar</label>
        <div class="d-flex align-items-center mb-2" style="gap: 1ch">
          <font-awesome-icon icon="fab fa-linkedin" style="font-size: 32px" />
          <input
            type="text"
            class="form-control"
            id="linkedin"
            v-model="links.linkedin"
            placeholder="Linkedin"
          />
        </div>
        <div class="d-flex align-items-center mb-2" style="gap: 1ch">
          <img
            src="~/assets/teams.svg"
            alt="Logo do Microsoft Teams"
            height="28px"
            width="28px"
          />
          <input
            type="text"
            class="form-control"
            id="teams"
            v-model="links.teams"
            placeholder="Teams"
          />
        </div>
        <div class="d-flex align-items-center mb-2" style="gap: 1ch">
          <font-awesome-icon icon="fab fa-whatsapp" style="font-size: 32px" />
          <input
            type="text"
            class="form-control"
            id="whatsapp"
            v-model="links.whatsapp"
            placeholder="Whatsapp"
          />
        </div>
      </div>
    </form>
    <button @click="submit" class="form-btn mb-3">Salvar</button>
    <p style="text-align: center; color: #aaa">
      <small>Os campos marcados com * são obrigatórios.</small>
    </p>
  </div>
</template>

<script>
import swal from "sweetalert2";

export default {
  name: "Cadastro",
  data() {
    return {
      name: "",
      email: this.$route.query.email,
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
    };
  },
  methods: {
    submit() {
      if (!this.email) this.$router.push("/");
      if (this.name && this.position && this.level) {
        let params = {
          name: this.name,
          email: this.email,
          isMentor: this.isMentor,
          position: this.position,
          level: this.level,
          techs: this.techs.split(","),
          links: this.links,
          //picture: this.picture
        };
        console.log(params);
      } else {
        swal.fire({
          icon: "error",
          title: "Ops...",
          text: "Preencha todos os campos obrigatórios para prosseguir!",
          footer:
            "<i><small>Campos obrigatórios são marcados com asterisco.</small></i>",
        });
      }
    },
    //As funções abaixo são claramente refatoráveis.
    selectPosition(id) {
      let allPositions = document.querySelectorAll(".position-input");
      allPositions.forEach((element) => {
        element.classList.remove("selected");
      });
      let selectedElement = document.getElementById(id);
      selectedElement.classList.add("selected");
    },
    selectLevel(id) {
      let allLevels = document.querySelectorAll(".level-input");
      allLevels.forEach((element) => {
        element.classList.remove("selected");
      });
      let selectedElement = document.getElementById(id);
      selectedElement.classList.add("selected");
    },
    selectMentor(id) {
      let allMentors = document.querySelectorAll(".mentor-input");
      allMentors.forEach((element) => {
        element.classList.remove("selected");
      });
      let selectedElement = document.getElementById(id);
      selectedElement.classList.add("selected");
    },
  },
  computed: {
    userEmail() {
      return this.$route.params.email;
    },
  },
};
</script>

<style scoped>
* {
  font-family: "Manrope";
}

form {
  padding: 20px;
}

.form-check {
  background-color: #ffffff;
  border: solid 2px #d3d3d3;
  border-radius: 20px;
  cursor: pointer;
  box-shadow: 0px 4px 4px 0px #00000040;
  font-weight: bold;
  min-width: 100px;
  justify-content: center;
}

.form-control::placeholder {
  font-size: 12px;
}

.form-check input {
  position: absolute;
  opacity: 0;
  cursor: pointer;
  height: 0;
  width: 0;
}

.form-check-label {
  cursor: pointer;
  padding: 10px;
}

.form-check:hover {
  background-color: #5251a2;
  color: #ffffff;
}

.selected {
  background-color: #5251a2;
  color: #ffffff;
}

.form-group input {
  border-radius: 20px;
}

.form-title {
  font-size: 1.5rem;
}

.form-btn {
  background: #5251a2;
  border-radius: 20px;
  padding: 10px 30px;
  border: 0;
  font-size: 14px;
  font-weight: bold;
  color: #ffffff;
}
</style>
