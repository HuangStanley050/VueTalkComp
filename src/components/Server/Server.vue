<template>
  <li @click="showDetail" class="list-group-item">Server #{{ server.id }}</li>
</template>

<script>
import { serverBus } from "../../main";
export default {
  props: ["server"],
  name: "Server",
  methods: {
    showDetail() {
      console.log(this.server.status);
      serverBus.$emit("showDetail", this.server);
    }
  }
};
</script>

<style>
li {
  cursor: pointer;
}
</style>
