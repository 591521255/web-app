<!-- TODO: Check for duplicate user ids by querying the server -->
<script setup>
import { RouterLink, RouterView } from "vue-router";
import cookies from "vue-cookies";
import MainPage from "@/components/Header.vue";
import { useI18n } from 'vue-i18n';
const { t } = useI18n({
  //inheritLocale: true,
  //useScope: 'local'
})
</script>

<template id="container">
  <div class="main">

  </div>
  <header>
    <div id="app">
      <img alt = "Nerf logo" class = "logo" src="./assets/logo.png" width="300" height="300" />
    </div>
    <div class="wrapper">
      <MainPage msg="NeRF or Nothing!" />
      <nav>
        <RouterLink to="/">{{t('main_page.home')}}</RouterLink>
        <RouterLink to="/explain">{{t('about_page.About NeRF')}}</RouterLink>
        <RouterLink to="/contact">{{t('main_page.ourteam')}}</RouterLink>
      </nav>
    </div>
  </header>
  <RouterView />
</template>

<script>
import { useI18n } from 'vue-i18n'
export default {
  name: 'App',
  components: {
  },
  setup() {
    const { t } = useI18n({
      //inheritLocale: true,
      //useScope: 'local'
    })

    // Something todo ..

    return { t }
  }
}
</script>

<style>
@import "@/assets/base.css";

#app {
  /*max-width: 1280px;*/
  color: white;
  margin: 0 auto;
  padding: 2rem;

  font-weight: normal;

}


.logo {
  display: block;
  margin: 0 auto 2rem;
}

a,
.green {
  text-decoration: none;
  color: var(green);
  transition: 0.4s;
}

.darkgreen {
  color: hsla(160, 100%, 37%, 1);
}

@media (hover: hover) {
  a:hover {
    background-color: hsla(160, 100%, 37%, 0.2);
  }
}

nav {
  font-size: 12px;
  text-align: center;
  margin-top: 2rem;
}

nav a.router-link-exact-active {
  color: var(--color-text);
}

nav a.router-link-exact-active:hover {
  background-color: transparent;
}

nav a {
  display: inline-block;
  padding: 0 1rem;
  border-left: 1px solid var(--color-border);
}

nav a:first-of-type {
  border: 0;
}

body {
  display: block;
}

header {
  display: flex;
  place-items: center;
  padding-right: calc(var(--section-gap) / 2);
}

.logo {
  margin: 0;
}

nav {
  text-align: left;
  margin-left: -1rem;
  font-size: 1rem;

  padding: 1rem 0;
  margin-top: 1rem;
}
</style>
