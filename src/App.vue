<template>
  <div id="app">
    <div class="custom-header-container">
      <header class="header">
        <div class="container">
          <logo></logo>
          <header-status></header-status>
        </div>
      </header>
    </div>
    <div class="container">
      <div class="row">
        <services></services>
        <incidents></incidents>
      </div>
    </div>
  </div>
</template>

<script>
import HeaderStatus from './components/HeaderStatus.vue'
import Logo from './components/Logo.vue'
import Services from './components/Services.vue'
import Incidents from './components/Incidents.vue'

export default {
  name: "app",
  components: {
    Logo,
    HeaderStatus,
    Services,
    Incidents
  }
};
</script>
<style>
.custom-header-container{
  background-color: #374048;
  padding-top:15px;
  margin-bottom: 70px;
}
</style>
