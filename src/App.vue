<template>
  <div id="app">
    <a-layout>
      <Header />
      <Project />
      <Composer />
      <Login />
      <Register />
      <router-view />
      <Footer />
    </a-layout>
  </div>
</template>

<script>
import store from "./store";
import Header from "./components/Header.vue";
import Footer from "./components/Footer.vue";
import Composer from "./components/Composer.vue";
import Project from "./components/Project.vue";
import Login from "./components/Login.vue";
import Register from "./components/Register.vue";

export default {
  name: "app",
  components: {
    Header,
    Footer,
    Composer,
    Project,
    Register,
    Login
  },
  computed: {
    control() {
      return store.state.control;
    }
  },
  mounted() {
    if (this.$route.query.idea != undefined) {
      this.control.project = true;
    }
  }
};
</script>

<style>
@font-face {
  font-family: "IdeaFont";
  src: url("./assets/font/KlarnaText-Regular.woff") format("woff");
}

@font-face {
  font-family: "IdeaFontMedium";
  src: url("./assets/font/KlarnaText-Medium.woff") format("woff");
}

@font-face {
  font-family: "IdeaFontBold";
  src: url("./assets/font/KlarnaText-Bold.woff") format("woff");
}

@font-face {
  font-family: "IdeaHeadlineBold";
  src: url("./assets/font/KlarnaHeadline-Bold.woff") format("woff");
}

.shadow {
  box-shadow: 0 1px 6px 0 rgba(32, 33, 36, 0.28);
}

p {
  word-break: normal;
}

.floatWindow {
  position: fixed;
  top: 10%;
  left: 25%;
  width: 50%;
  height: 80%;
  background-color: white;
  z-index: 999;
  border-radius: 2px;
  overflow: scroll;
}

a-input {
  margin-bottom: 25px;
}

a-textarea {
  margin-bottom: 25px;
}

.floatBackground {
  position: fixed;
  top: 0%;
  left: 0%;
  width: 100%;
  height: 100%;
  background-color: black;
  z-index: 998;
  opacity: 0.4;
}

.floatWindow .container {
  float: left;
  width: 90%;
  margin-top: 0px;
  margin-bottom: 0px;
  margin-left: 5%;
}

.bounce {
  -webkit-animation: bounce 2s infinite;
  -moz-animation: bounce 2s infinite;
  -o-animation: bounce 2s infinite;
}

@-webkit-keyframes bounce {
  0%,
  20%,
  50%,
  80%,
  100% {
    -webkit-transform: translateY(0);
  }
  40% {
    -webkit-transform: translateY(-10px);
  }
  60% {
    -webkit-transform: translateY(-5px);
  }
}

@-moz-keyframes bounce {
  0%,
  20%,
  50%,
  80%,
  100% {
    -moz-transform: translateY(0);
  }
  40% {
    -moz-transform: translateY(-10px);
  }
  60% {
    -moz-transform: translateY(-5px);
  }
}

@-o-keyframes bounce {
  0%,
  20%,
  50%,
  80%,
  100% {
    -o-transform: translateY(0);
  }
  40% {
    -o-transform: translateY(-10px);
  }
  60% {
    -o-transform: translateY(-5px);
  }
}
@keyframes bounce {
  0%,
  20%,
  50%,
  80%,
  100% {
    transform: translateY(0);
  }
  40% {
    transform: translateY(-10px);
  }
  60% {
    transform: translateY(-5px);
  }
}
</style>
