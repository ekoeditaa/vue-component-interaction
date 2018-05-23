<template>
    <li class="list-group-item" @click="viewDetails" style="cursor: pointer">
        Server #{{ server.id }}
    </li>
</template>

<script>
import {eventBus} from '../../main.js';

export default {
    props: {
        server: Object
    },
    methods: {
        viewDetails() {
            eventBus.$emit('viewDetails', this.server)
        }
    }
}
</script>
