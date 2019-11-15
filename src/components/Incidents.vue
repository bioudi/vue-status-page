<template>
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
        <!-- <b-pagination
            v-model="currentPage"
            :total-rows="rows"
            :per-page="perPage"
        ></b-pagination> -->
        </div>
    </div>
</template>
<style scoped>
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