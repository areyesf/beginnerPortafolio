<template>
  <div id="app">
    <Nav/>
    <Content/>
  </div>
</template>

<script>
import Nav from "@/components/Nav";
import Content from "@/components/Content.vue";

export default {
  components: {
    Nav,
    Content,
  },
};
</script>
<style lang="scss">
//IMPORT FONT
@import url("https://fonts.googleapis.com/css2?family=Roboto:wght@100;900&display=swap");

// RESET STYLES
* {
  margin: 0;
  padding: 0;
  box-sizing: border-box;
}
body {
  font-family: "Roboto", sans-serif;
  min-height: 100vh;
}
</style>
