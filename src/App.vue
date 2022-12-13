<template>
  <nav class="navbar navbar-expand-lg navbar navbar-dark bg-dark">
    <div class="container-fluid">
      <span class="navbar-brand"><router-link to="/"><img width="200" height="60" src="../src/assets/logo.png"
            alt="" /></router-link></span>
      <button class="navbar-toggler" type="button" data-bs-toggle="collapse" data-bs-target="#navbarNavDropdown"
        aria-controls="navbarNavDropdown" aria-expanded="false" aria-label="Toggle navigation">
        <span class="navbar-toggler-icon"></span>
      </button>
      <div class="collapse navbar-collapse" id="navbarNavDropdown">
        <ul class="navbar-nav">
          <li class="nav-item">
            <a class="nav-link active" aria-current="page" href="#"><router-link to="/">Home</router-link></a>
          </li>
          <li class="nav-item">
            <a class="nav-link" href="#"><router-link to="/about">About us</router-link></a>
          </li>
          <li class="nav-item">
            <a class="nav-link" href="#"><router-link to="/portfolio">Portfolio</router-link></a>
          </li>
          <li class="nav-item">
            <a class="nav-link" href="#"><router-link to="/contact">Contact</router-link></a>
          </li>
        </ul>
      </div>
    </div>
  </nav>
  <div v-if="this.$route.name === 'about' || this.$route.name === 'home'">
    <GalerieGal />
  </div>
  <router-view v-slot="{ Component }">
    <transition name="route" made="out-in">
      <component :is="Component"></component>
    </transition>
  </router-view>
  <footer class="text-center text-white navbar-dark bg-dark">
    <!-- Grid container -->
    <div class="container p-4 pb-0">
      <section class="">
        <p class="d-flex justify-content-center align-items-center">
          <span class="me-3">Contact </span>
          <button type="button" class="btn btn-outline-light btn-rounded">
            <router-link to="/contact">Sign up!</router-link>
          </button>
        </p>
      </section>
    </div>
    <div class="text-center p-3" style="background-color: rgba(0, 0, 0, 0.2)">
      © 2022 Copyright:
      <a class="text-white"><router-link to="/">YBOP.com</router-link></a>
    </div>
  </footer>
</template>

<script>
import GalerieGal from "@/components/GalerieGal.vue";
export default {
  components: {
    GalerieGal,
  },
};
</script>

<style >
html {
  scroll-behavior: smooth;
}

#app {
  background-color: rgb(240, 240, 240);
}

span {
  color: #ffffff;
}

nav a {
  color: #2c3e50;
  font-family: Century Gothic, CenturyGothic, AppleGothic, sans-serif;
}

a.router-link-exact-active {
  color: #e9f4ff;
  font-family: Century Gothic, CenturyGothic, AppleGothic, sans-serif;
  font-size: 30px;
}

.container .content {
  padding: 80px 20%;
}

/* ss */

nav ul {
  color: white;
  text-transform: uppercase;
  list-style-type: none;
  font-family: Century Gothic, CenturyGothic, AppleGothic, sans-serif;
}

nav li {
  line-height: 2em;
  letter-spacing: 0.2em;
  font-family: Century Gothic, CenturyGothic, AppleGothic, sans-serif;
}

nav a {
  font-size: 20px;
  text-decoration: none;
  color: white;
  font-weight: 100;
  font-family: Century Gothic, CenturyGothic, AppleGothic, sans-serif;
}

nav li::after {
  content: "";
  display: block;
  width: 0;
  height: 2px;
  background: rgb(255, 255, 255);
  transition: 0.3s;
}

nav li:hover::after {
  width: 100%;
  transition: 0.3s;
}

p {
  line-height: 1.5em;
  font-family: Century Gothic, CenturyGothic, AppleGothic, sans-serif;
}

h1 {
  color: rgb(0, 0, 0);
  font-family: Century Gothic, CenturyGothic, AppleGothic, sans-serif;
}

h5,
h4,
p {
  color: #000000;
  font-family: Century Gothic, CenturyGothic, AppleGothic, sans-serif;
}

.portfolio {
  background-image: url("assets/blackOcean.jpg");
  height: 1100px;
  background-position: center;
  background-repeat: no-repeat;
  background-size: cover;
}

.WelcomeText {
  color: white;
  margin: center auto;
  text-align: center;
  margin-top: 100px;
}

/* route transition */
.route-enter-form {
  opacity: 0;
  transform: translateX(100px);
}

.route-enter-active {
  transition: all 0.3s ease-out;
}

.route-leave-to {
  opacity: 0;
  transform: translateX(-100px);
}

.route-leave-active {
  transition: all 0.3s ease-in;
}
</style>
