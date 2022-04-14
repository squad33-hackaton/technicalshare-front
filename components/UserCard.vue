<template>
  <div class="user-card fade-in" @click="$emit('click')">
    <!-- <img src="" alt="" class="user-card-avatar">  -->
    <font-awesome-icon icon="fa-solid fa-user" style="font-size: 3rem" />
    <div class="user-card-texts">
      <p class="user-card-tag" v-if="isMentor">Mentor</p>
      <p class="user-card-title">{{ username }}</p>
      <p class="user-card-subtext">{{ position }} {{ level }}</p>
      <p class="user-card-techs">
        <small>{{ techs.split(";").join(", ") }}</small>
      </p>
    </div>
  </div>
</template>

<script>
export default {
  name: "UserCard",
  props: {
    username: {
      type: String,
      required: true,
    },
    position: {
      type: String,
      required: true,
    },
    level: {
      type: String,
      required: true,
    },
    isMentor: {
      type: Boolean,
      required: true,
    },
    techs: {
      type: String,
      required: true,
    },
  },
};
</script>

<style scoped>
p {
  font-family: "Manrope";
}

.user-card {
  background-color: #ffffff;
  display: flex;
  align-items: center;
  border-radius: 15px;
  gap: 3rem;
  padding: 20px 40px;
  width: 100%;
  cursor: pointer;
  box-shadow: rgba(99, 99, 99, 0.2) 0px 2px 8px 0px;
}

.user-card:hover {
  background-color: #a6a3a3;
}

.user-card-texts p {
  margin: 0;
}

.user-card-title {
  font-size: 1.5rem;
  font-weight: bold;
}

.user-card-subtext {
  font-size: 1.2rem;
}

.user-card-tag {
  font-size: 12px;
  font-weight: bold;
  padding: 2.5px 5px;
  background-color: #ff7a00;
  border-radius: 20px;
  text-align: center;
  max-width: 65px;
}

.fade-in {
  animation: fadeIn ease 500ms;
  -webkit-animation: fadeIn ease 500ms;
  -moz-animation: fadeIn ease 500ms;
  -o-animation: fadeIn ease 500ms;
  -ms-animation: fadeIn ease 500ms;
}
@keyframes fadeIn {
  0% {
    opacity: 0;
  }
  100% {
    opacity: 1;
  }
}

@-moz-keyframes fadeIn {
  0% {
    opacity: 0;
  }
  100% {
    opacity: 1;
  }
}

@-webkit-keyframes fadeIn {
  0% {
    opacity: 0;
  }
  100% {
    opacity: 1;
  }
}

@-o-keyframes fadeIn {
  0% {
    opacity: 0;
  }
  100% {
    opacity: 1;
  }
}

@-ms-keyframes fadeIn {
  0% {
    opacity: 0;
  }
  100% {
    opacity: 1;
  }
}
@media (max-width: 767px) {
  .user-card {
    padding: 10px 20px;
    width: 100%;
    gap: 5ch;
    min-height: 140px;
  }

  .user-card-title {
    font-size: 16px;
  }

  .user-card-subtext {
    font-size: 14px;
  }
}
</style>
