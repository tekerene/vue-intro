/* eslint-disable vue/no-parsing-error */
<template>
  <div id="app">
    <h1>{{ title }}</h1>
    <h2>{{ title2 }}</h2>
    <input type="text" v-model="title" />
    <!-- <p>{{ text }}</p> -->
    <hr />
    <div>
      <app-HelloWorld
        v-on:changeTitle="title = $event"
        v-bind:newTitle="title"
        :newText="text"
        v-on:changeName="title2 = $event"
      ></app-HelloWorld>
      <hr />
      <app-firstChild
        v-on:sendText="text = $event"
        v-bind:newText="text"
      ></app-firstChild>
    </div>
    <hr />
    <button @click="currentComponent = 'one'">Blue Template</button>
    <button @click="currentComponent = 'two'">Teal Template</button>
    <keep-alive>
      <component :is="currentComponent"></component>
    </keep-alive>
  </div>
</template>

<script>
import HelloWorld from "./components/HelloWorld.vue";
import firstChild from "./components/firstchild.vue";
import one from "./components/one.vue";
import two from "./components/two.vue";

export default {
  data() {
    return {
      title: "Our Title From Parent",
      text: "I am coming from App Vue",
      currentComponent: "one",
      title2: ""
    };
  },
  name: "app",
  components: {
    "app-HelloWorld": HelloWorld,
    "app-firstChild": firstChild,
    // eslint-disable-next-line vue/no-unused-components
    one,
    // eslint-disable-next-line vue/no-unused-components
    two
  }
};
</script>

<style lang="scss">
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
