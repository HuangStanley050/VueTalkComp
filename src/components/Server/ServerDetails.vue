<template>
  <div class="col-xs-12 col-sm-6">
    <p v-if="!server">Please select a server</p>
    <div v-else>
      <p>Server # {{ server.id }}</p>
      <p>Status: {{ server.status }}</p>
    </div>
    <button @click="resetServer">Reset Server</button>
  </div>
</template>

<script>
import { serverBus } from "../../main";
export default {
  data: function() {
    return {
      server: null
    };
  },
  methods: {
    resetServer() {
      this.server.status = "Normal";
    }
  },
  created() {
    serverBus.$on("showDetail", server => (this.server = server));
  }
};
</script>

<style></style>
