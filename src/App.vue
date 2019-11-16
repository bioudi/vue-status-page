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
        <services :services="config.services" :retryInterval="config.retryInterval"></services>
        <incidents v-if="config.jiraCloud.enabled"></incidents>
        <div class="col-lg-8" v-else>
          <h3 class="text-center">Jira cloud integration is comming soon</h3>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
import HeaderStatus from './components/HeaderStatus.vue'
import Logo from './components/Logo.vue'
import Services from './components/Services.vue'
import Incidents from './components/Incidents.vue'
import config from '../config.json'

export default {
  name: "app",
  beforeCreate(){
    Object.keys(config.services).forEach((key) => {
        config.services[key].fetched = false
    })
  },
  data(){
    return {
      config: config
    }
  },
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
h3{
  color: #374048;
}
</style>
