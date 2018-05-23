<template>
    <div class="col-xs-12 col-sm-6">
        <p v-if="!server">Server Details are currently not updated</p>
        <p v-else>Server id: {{ server.id }} <br /> Server status: {{ server.status }}</p>
        <button @click="resetStatus"> Reset status to normal </button>
    </div>

</template>

<script>
import { eventBus } from "../../main";
export default {
    props: {
        server: Object
    },
    created() {
        eventBus.$on('viewDetails', (server) => {
            this.server = server;
        })
    },
    methods: {
        resetStatus() {
            this.server.status = "Normal";
        }
    }
}
</script>

<style>

</style>
