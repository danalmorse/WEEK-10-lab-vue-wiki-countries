<script setup>
  /*import HelloWorld from "./components/HelloWorld.vue";*/
  import NavBar from "./components/NavBar.vue";
  import CountriesList from "./components/CountriesList.vue";
  import countries from "./countries.json"; /*iteracion 2*/
  
  /*import CountryDetails from "./components/CountryDetails.vue";*/
  /*const countries2 = ref (countries)*/
  countries.sort((a, b) => {
    if (a.name.common > b.name.common) return 1;
    if (a.name.common < b.name.common) return -1;
    return 0;
  });
</script>

<template>
  <div class="app">
    <NavBar />
    <!--<HelloWorld />-->
    <div className="container">
      <div className="row">
        <CountriesList :countries="countries" /> <!--iteracion 2: conectando json a CountriesList por props -->
        <router-view />
      </div>
    </div>
    <!--<div className="row"> Iteracion 1.3 y 1.4
    <div class="col-5" style="max-height: 90vh; overflow: scroll"> Change
      <CountriesListss></CountriesListss>
      <CountryDetailsss></CountryDetails>
    </div>-->
    
  </div>
</template>

<style>
body {
  margin: 0;
  font-family: -apple-system, BlinkMacSystemFont, 'Segoe UI', 'Roboto', 'Oxygen',
    'Ubuntu', 'Cantarell', 'Fira Sans', 'Droid Sans', 'Helvetica Neue',
    sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
}

code {
  font-family: source-code-pro, Menlo, Monaco, Consolas, 'Courier New',
    monospace;
}

.app {
  text-align: center;
}

.app-logo {
  height: 40vmin;
  pointer-events: none;
}

@media (prefers-reduced-motion: no-preference) {
  .app-logo {
    animation: app-logo-spin infinite 20s linear;
  }
}

.app-header {
  background-color: #282c34;
  min-height: 100vh;
  display: flex;
  flex-direction: column;
  align-items: center;
  justify-content: center;
  font-size: calc(10px + 2vmin);
  color: white;
}

.app-link {
  color: #61dafb;
}

@keyframes app-logo-spin {
  from {
    transform: rotate(0deg);
  }
  to {
    transform: rotate(360deg);
  }
}

</style>
