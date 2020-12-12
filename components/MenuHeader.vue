<template>
  <div class="menu" style="height:100%">
    <menu-blob class="closed" height="10vh" />
    <div class="menuitems">
      <div>Home</div>
      <div>Magicians</div>
      <div>Contact</div>
    </div>
  </div>
</template>
<style scoped>
.menu {
  height: 100%;
  color: white;
  font-family: "rift_softregular";
}
.greypage .menu {
  color: #333333;
}
.menu .closed {
  position: absolute;
}
.menuitems {
  z-index: 100;
  position: absolute;
  width: 32vh;
  padding-left: 8vh;

  height: 10vh;
  display: flex;
  justify-content: space-around;
  align-items: center;
}
.menu {
  grid-area: header;
  margin-top: -2vh;
  margin-left: -33vh;
  transition: 0.3s;
}
.menu:hover {
  margin-left: 0;
}
</style>
