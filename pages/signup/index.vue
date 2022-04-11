<template>
  <div class="d-flex flex-column justify-content-center align-items-center p-3" style="min-height: 100vh; background-color: #F0F0F0;">
    <form>
      <div class="form-group">
        <label for="name" class="form-title">Qual o seu nome?</label>
        <input type="text" class="form-control" id="name" v-model="name">
      </div>
      <div class="form-group">
        <label for="name" class="form-title">Com o que você trabalha?</label><br>
        <div class="form-check form-check-inline mb-3">
          <input class="form-check-input" type="checkbox" id="frontend" value="Front-end" v-model="tags">
          <label class="form-check-label" for="frontend">Front-end</label>
        </div>
        <div class="form-check form-check-inline mb-3">
          <input class="form-check-input" type="checkbox" id="backend" value="Back-end" v-model="tags">
          <label class="form-check-label" for="backend">Back-end</label>
        </div>
        <div class="form-check form-check-inline mb-3">
          <input class="form-check-input" type="checkbox" id="fullstack" value="Full Stack" v-model="tags">
          <label class="form-check-label" for="fullstack">Full Stack</label>
        </div>
        <div class="form-check form-check-inline mb-3">
          <input class="form-check-input" type="checkbox" id="ux" value="UX Designer" v-model="tags">
          <label class="form-check-label" for="ux">UX Design</label>
        </div>
        <div class="form-check form-check-inline">
          <input class="form-check-input" type="checkbox" id="ui" value="UI Designer" v-model="tags">
          <label class="form-check-label" for="ui">UI Design</label>
        </div>
      </div>
      <div class="form-group">
        <label for="name" class="form-title">Qual o seu nível de senioridade?</label><br>
        <div class="form-check form-check-inline mb-3">
          <input class="form-check-input" type="radio" id="trainee" value="Trainee" v-model="level">
          <label class="form-check-label" for="trainee">Trainee</label>
        </div>
        <div class="form-check form-check-inline mb-3">
          <input class="form-check-input" type="radio" id="junior" value="Júnior" v-model="level">
          <label class="form-check-label" for="junior">Júnior</label>
        </div>
        <div class="form-check form-check-inline mb-3">
          <input class="form-check-input" type="radio" id="pleno" value="Pleno" v-model="level">
          <label class="form-check-label" for="pleno">Pleno</label>
        </div>
        <div class="form-check form-check-inline mb-3">
          <input class="form-check-input" type="radio" id="senior" value="Senior" v-model="level">
          <label class="form-check-label" for="senior">Senior</label>
        </div>
      </div>  
        <div class="form-group">
          <label for="tech" class="form-title">Com qual tecnologia você trabalha?</label>
          <input type="text" class="form-control" id="tech" v-model="tech">
        </div>
        <div class="form-group">
          <label class="form-title">Links de comunicação</label>
          <input type="text" class="form-control mb-3" id="linkedin" v-model="links.linkedin" placeholder="Linkedin">
          <input type="text" class="form-control mb-3" id="teams" v-model="links.teams" placeholder="Teams">
          <input type="text" class="form-control mb-3" id="whatsapp" v-model="links.whatsapp" placeholder="Whatsapp">
        </div>
      <p>Áreas selecionadas: {{ tags }}</p>
      <!-- Inserir type=submit aqui para enviar o form caso necessário -->
    </form>
    <button @click="submitTest" class="btn btn-primary">Confirmar</button>  
  </div>
</template>

<script>
export default {
  name: 'Cadastro',
  data() {
    return {
      name: "",
      email: this.$route.query.email,
      password: "",
      passwordConfirmation: "",
      tags: [],
      tech: "",
      links: {
        linkedin: "",
        teams: "",
        whatsapp: ""
      },
      isClicked: false,
    }
  },
  methods: {
    submitTest() {
      console.log(this.name)
      console.log(this.email)
      console.log(this.tags)
      console.log(this.tech)
      console.log(this.links)
    }
  },
  computed: {
    userEmail() {
      return this.$route.params.email
    }
  }
}
</script>

<style scoped>
* {
  font-family: 'Manrope';
}

.form-check {
  background-color: #aaaaaa;
  border-radius: 15px;
  cursor: pointer;
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
  background-color: #ff932e;
}

.clicked {
  background-color: #ff932e;
}

.form-title {
  font-size: 1.3rem;
}
</style>
