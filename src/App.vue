<template>
  <div id="app">
    <h1>This is a POC of a custom context menu in vue</h1>
    <p>&nbsp;</p>
    <TabsComponent />
    <p>&nbsp;</p>
    <small>Marny Lopez</small>
  </div>
</template>

<script>
import TabsComponent from "./components/TabsComponent";

export default {
  name: "App",
  components: {
    TabsComponent,
  },
};
</script>

<style>
#app {
  font-family: "Avenir", Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin: 60px;
}
</style>
