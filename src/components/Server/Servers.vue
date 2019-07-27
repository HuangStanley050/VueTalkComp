<template>
  <div class="col-xs-12 col-sm-6">
    <ul class="list-group">
      <Server :key="server.id" :server="server" v-for="server in servers" />
    </ul>
  </div>
</template>
s:
<script>
import Server from "./Server.vue";
export default {
  name: "Servers",
  data: function() {
    return {
      servers: [
        { id: 1, status: "Normal" },
        { id: 2, status: "Critical" },
        { id: 3, status: "Unknown" },
        { id: 4, status: "Normal" }
      ]
    };
  },
  components: {
    Server
  }
};
</script>

<style></style>
