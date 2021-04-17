<template>
  <div id="app">
    <Header />
    <TodoStack />
    <Footer />
  </div>
</template>

<script>
import Header from "@/components/Header";
import TodoStack from "@/components/TodoStack";
import Footer from "@/components/Footer";

export default {
  name: "App",
  components: {
    Header,
    TodoStack,
    Footer,
  },
};
</script>

<style lang="scss">
// add style
</style>
