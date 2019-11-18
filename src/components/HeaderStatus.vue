<template>
    <div class="row">
        <div class="col-lg-12">
            <div class="header-incidents-outer-container">
            <div class="header-incidents-inner-container">
                <div v-if="isLoading" class="page-status status-none">
                  <span class="status font-large">Loading ...</span>
                </div>
                <template v-else>
                  <div v-if="isAllGood" class="page-status status-none status-green">
                    <span class="status font-large">All Systems Operational :)</span>
                  </div>
                  <div v-else class="page-status status-none status-red">
                    <span class="status font-large">Ouups something went wrong :(</span>
                  </div> 
                </template>
            </div>
            </div>
        </div>
    </div>
</template>
<script>
export default {
  created(){
    this.$root.$on('isAllGood', (response) => {
      this.isAllGood = response
      this.isLoading = false
    })
  },
  data(){
    return {
      isLoading: true,
      isAllGood: null
    }
  }
}
</script>
<style scoped>
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
  background-color: #374048;
  padding: 0.75rem 1.25rem;
  color: #fff;
  border: 1px solid rgba(0,0,0,0.1);
  border-radius: 4px;
}
.status-green{
  background-color: #71bf60;
}
.status-red{
  background-color: #f36d6f;
}
</style>