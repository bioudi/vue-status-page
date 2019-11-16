<template>
    <div class="components-section col-lg-4">
        <b-card no-body header="Services">
            <b-list-group flush>
                <b-list-group-item :href="service.endpoint" target="_blank" v-for="(service, index) in services" :key="index">
                <span>{{ index }}</span>
                <div class="status-icon">
                    <template v-if="service.fetched">
                        <i v-if="service.available" class="fas fa-check-circle"></i>
                        <i v-else class="fas fa-times-circle"></i>
                    </template>
                    <template v-else>
                        <i class="fas fa-circle-notch fa-spin"></i>
                    </template>
                </div>
                </b-list-group-item>
            </b-list-group>
        </b-card>
    </div>
</template>
<script>
export default {
    props:{
        services:{
            type: Object,
            default: null
        },
        retryInterval:{
            type: Number,
            default: 30
        }
    },
    async mounted(){
        this.pingServicesAndNotify()
        setInterval(async () => {
            this.pingServicesAndNotify()
        }, this.retryInterval * 1000);
    },
    data(){
        return {
            somethingWentWrong: []
        }
    },
    methods:{
        async pingServicesAndNotify(){
            await this.pingServices();
            this.$root.$emit('isAllGood', !this.somethingWentWrong.includes(true));
        },
        async pingServices(){
            this.somethingWentWrong = []
            let requests = []
            Object.keys(this.services).forEach((key) => requests.push(this.fetchHost(this.services[key])))
            await Promise.all(requests)
        },
        fetchHost(service){
            const mode = service.isWebsite ? { mode: 'no-cors'} : {}
            return fetch(service.endpoint, mode)
            .then((resp) => {
                let error = false;
                service.available = true
                if (!resp.ok || resp.status != 200) {
                    service.available = false
                    error = true
                }
                if (resp.type == "opaque") {
                    service.available = true
                    error = false
                }
                this.somethingWentWrong.push(error)
            })
            .catch(() => {
                service.available = false
                this.somethingWentWrong.push(true)
            })
            .finally(() => service.fetched = true)
        }
    }
}
</script>
<style scoped>
.loader{
    padding: 1rem 0rem;
    margin: 0 auto;
}
.components-section{
  margin-bottom: 2rem;
}
.status-icon {
  float: right;
}
.fas {
    font-size: 1.2rem;
}
.status-icon .fa-check-circle{
  color: #71bf60;
}
.status-icon .fa-times-circle{
  color: #f36d6f;
}
</style>