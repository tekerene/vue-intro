<template>
  <div id="hello">
    <h1>{{ newTitle }}</h1>
    <button @click="changeTitle">Change Title</button>
    <button @click="changeName">change Name</button>
    <!-- <h2>{{ anyNam }}</h2> -->
    <h4>{{ msg }}</h4>
    <p>{{ newText }}</p>
  </div>
</template>

<script>
import { eventBus } from "../main.js";
export default {
  props: ["newTitle", "newText"],
  name: "hello",
  data() {
    return {
      // eslint-disable-next-line vue/no-dupe-keys
      msg: "Welcome From Hello World",
      anyName: "eventBus for Hello"
    };
  },
  methods: {
    changeTitle() {
      this.newTitle = "Title was Change by Hello World Child";
      this.$emit("changeTitle", this.newTitle);
      eventBus.$emit("send-name", this.anyName);
    },
    changeName() {
      this.anyNam = "this is sarko from sark techno";
      this.$emit("changeName", this.anyNam);
    }
  }
};
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped lang="scss">
h3 {
  margin: 40px 0 0;
}
ul {
  list-style-type: none;
  padding: 0;
}
li {
  display: inline-block;
  margin: 0 10px;
}
a {
  color: #42b983;
}
</style>
