<template>
  <div class="Blue">
    <h1>Blue Template</h1>
  </div>
</template>

<script>
export default {
  created() {
    alert("Blue Template Create");
  }
};
</script>
<style scoped>
.Blue {
  width: 400px;
  height: 200px;
  padding: 20px;
  text-align: center;
  background: royalblue;
}
</style>
