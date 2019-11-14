<template>
  <div id="app">
    <div class="custom-header-container">
      <header class="header">
        <div class="container">
          <div class="row">
            <div class="logo col-lg-3">
              <img src="/status-logo.png" alt="logo" width="60px" height="48px" />
            </div>
          </div>
          <div class="row">
            <div class="col-lg-12">
              <div class="header-incidents-outer-container">
                <div class="header-incidents-inner-container">
                  <div class="page-status status-none">
                    <span class="status font-large">All Systems Operational</span>
                  </div>
                </div>
              </div>
            </div>
          </div>
        </div>
      </header>
    </div>
    <div class="container">
      <div class="row">
        <div class="components-section col-lg-4">
          <b-card no-body header="Services">
            <b-list-group flush>
              <b-list-group-item href="#">
                <span>Backend Digital</span>
                <div class="status-icon">
                  <i class="fas fa-check-circle"></i>
                </div>
              </b-list-group-item>
              <b-list-group-item href="#">
                <span>Webapp</span>
                <div class="status-icon">
                  <i class="fas fa-check-circle"></i>
                </div>
              </b-list-group-item>
              <b-list-group-item href="#">
                <span>salesforce</span>
                <div class="status-icon">
                  <i class="fas fa-check-circle"></i>
                </div>
              </b-list-group-item>
              <b-list-group-item href="#">
                <span>Soa</span>
                <div class="status-icon">
                  <i class="fas fa-check-circle"></i>
                </div>
              </b-list-group-item>
            </b-list-group>
          </b-card>
        </div>
        <div class="incidents-list col-lg-8">
          <div>
            <b-card class="incident" title="Cloud Control Panel and API Issues">
              <b-card-text>
                Some quick example text to build on the
                <em>card title</em> and make up the bulk of the card's
                content.
              </b-card-text>

              <b-card-text>A second paragraph of text in the card.</b-card-text>

              <a href="#" class="card-link">Incident details</a>
            </b-card>
            <b-card class="incident" title="Cloud Control Panel and API Issues">
              <b-card-text>
                Some quick example text to build on the
                <em>card title</em> and make up the bulk of the card's
                content.
              </b-card-text>

              <b-card-text>A second paragraph of text in the card.</b-card-text>

              <a href="#" class="card-link">Incident details</a>
            </b-card>
            <b-pagination
              v-model="currentPage"
              :total-rows="rows"
              :per-page="perPage"
            ></b-pagination>
          </div>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  name: "app",
  data(){
    return {
      currentPage: 1,
      rows: 10,
      perPage: 2
    }
  }
};
</script>

<style>
.custom-header-container{
  background-color: #374048;
  padding-top:15px;
  margin-bottom: 70px;
}
.header-incidents-outer-container{
  position: relative;
  top: 20px;
}
.header-incidents-inner-container{
  border-radius: 4px;
  box-shadow: 0 3px 6px rgba(0, 0, 0, 0.1);
  background: white;
  padding: 30px 35px;
}
.status-none{
  background-color: #71bf60;
  padding: 0.75rem 1.25rem;
  color: #fff;
  border: 1px solid rgba(0,0,0,0.1);
  border-radius: 4px;
}
.components-section{
  margin-bottom: 2rem;
}
.status-icon {
  float: right;
}
.status-icon .fa-check-circle{
  color: #71bf60;
  font-size: 1.2rem;
}
.card-link{
  color: #3686be;
}
.incident{
  margin-bottom: 1rem;
}
.page-item.active .page-link {
    color: #fff !important;
    background-color: #3686be !important;
    border-color: #3686be !important;
}
.page-link {
    color: #3686be !important;
}
</style>
