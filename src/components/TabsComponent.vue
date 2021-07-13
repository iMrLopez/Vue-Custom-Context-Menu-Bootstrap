<template>
  <div>
    <b-tabs>
      <b-tab title="1"><p>I'm the 1 tab</p></b-tab>
      <b-tab title="2"><p>I'm the 2 tab</p></b-tab>
      <b-tab title="3"><p>I'm the 3 tab</p></b-tab>
      <b-tab title="4"><p>I'm the 4 tab</p></b-tab>
      <b-tab title="5"><p>I'm the 5 tab</p></b-tab>
      <b-tab title="6"><p>I'm the 6 tab</p></b-tab>
      <b-tab title="Disabled" disabled><p>I'm a disabled tab!</p></b-tab>
    </b-tabs>
    <CustomContextMenu ref="customContextMenu" />
  </div>
</template>

<script>
import CustomContextMenu from "./CustomContextMenu";

export default {
  name: "TabsComponent",
  components: {
    CustomContextMenu,
  },
  props: {
    msg: String,
  },
  data: () => ({}),
  mounted() {
    this.$nextTick(function () {
      const tab_list = document.getElementsByClassName("nav-link");
      for (var i = 0; i < tab_list.length; i++) {
        tab_list[
          i
        ].oncontextmenu = this.$refs.customContextMenu.openContextMenu;
      }
    });
  },
};
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
</style>
