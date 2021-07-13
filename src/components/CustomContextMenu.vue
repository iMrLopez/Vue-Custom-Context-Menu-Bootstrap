<template>
  <div v-show="contextMenuVisible">
    <ul :style="{ left: left + 'px', top: top + 'px' }" class="contextmenu">
      <li @click="selectedContextMenu()">A</li>
      <li @click="selectedContextMenu()">B</li>
      <li @click="selectedContextMenu()">C</li>
      <li @click="selectedContextMenu()">D</li>
      <li @click="selectedContextMenu()">E</li>
      <li @click="selectedContextMenu()">F</li>
      <li @click="selectedContextMenu()">G</li>
    </ul>
  </div>
</template>

<script>
export default {
  name: "CustomContextMenu",
  props: ["bus"],
  data: () => ({
    top: 1,
    left: 1,
    contextMenuVisible: false,
  }),
  created: function () {
    window.addEventListener("click", this.clickedOutsideOfContextMenu);
  },
  destroyed: function () {
    window.removeEventListener("click", this.clickedOutsideOfContextMenu);
  },
  methods: {
    openContextMenu(e) {
      e.preventDefault(); //Prevent the default menu from popping up
      this.contextMenuVisible = true;
      this.left = e.clientX + 10;
      this.top = e.clientY + 10;
      console.log(e.target.text.trim()); // TODO prepare contextual options
    },
    selectedContextMenu(e) {
      this.contextMenuVisible = false;
    },
    clickedOutsideOfContextMenu(e) {
      this.contextMenuVisible = false;
    },
  },
};
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
.contextmenu {
  width: 100px;
  margin: 0;
  border: 1px solid #ccc;
  background: #fff;
  z-index: 3000;
  position: absolute;
  list-style-type: none;
  padding: 5px 0;
  border-radius: 4px;
  font-size: 14px;
  color: #333;
  box-shadow: 2px 2px 3px 0 rgba(0, 0, 0, 0.2);
}
.contextmenu li {
  margin: 0;
  padding: 0px 22px;
}
.contextmenu li:hover {
  background: #f2f2f2;
  cursor: pointer;
}
.contextmenu li button {
  color: #2c3e50;
}
</style>
