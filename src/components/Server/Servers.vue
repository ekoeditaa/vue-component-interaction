<template>
    <div class="col-xs-12 col-sm-6">
        <ul class="list-group" v-for="server in servers">
            <serverRow :server="server"> </serverRow>
        </ul>
    </div>
</template>

<script>
import ServerRow from './ServerRow.vue';

export default {
  data: function() {
    return {
        servers: [
            { id: 1, status: "Normal"},
            { id: 2, status: "Critical"},
            { id: 3, status: "Normal"},
            { id: 4, status: "Unknown"},
            { id: 5, status: "Normal"},
        ]
    };
  },
  components: {
      serverRow: ServerRow,
  }
};
</script>

<style>
</style>
