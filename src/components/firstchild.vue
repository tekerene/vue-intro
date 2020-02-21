<template>
  <div>
    <h4>{{ msg }}</h4>
    <button @click="sendText">Send Text</button>
    <h3>{{ name }}</h3>
    <!-- <h3>{{ newText }}</h3> -->
  </div>
</template>

<script>
import { eventBus } from "../main.js";
export default {
  name: "firstChild",
  props: ["newText"],
  data() {
    return {
      // eslint-disable-next-line vue/no-dupe-keys
      msg: "hello from first child component",
      text: "I am coming from First Child Component",
      name: " "
    };
  },
  methods: {
    sendText() {
      this.newTex = this.text;
      // eslint-disable-next-line no-unreachable
      this.$emit("sendText", this.newTex);
    }
  },
  created() {
    eventBus.$on("send-name", function(nname) {
      this.name = nname;
    });
  }
};
</script>
