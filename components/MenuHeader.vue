<template>
  <div class="menu" style="height:100%">
    <menu-blob class="closed" height="10vh" />
    <div class="menuitems">
      <div><nuxt-link to="/"> Home</nuxt-link></div>
      <div><a href="https://magicseth.com/magicians">Magicians</a></div>
      <div><nuxt-link to="/about">About</nuxt-link></div>
    </div>
  </div>
</template>
<style scoped>
.offline .menu {
  display: none;
}
a {
  text-decoration: none;
  color: white;
}
.menu {
  height: 100%;
  color: white;
  font-family: "rift_softregular";
}
.greypage .menu {
  color: #333333;
}
.greypage a {
  text-decoration: none;
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
a:hover {
  font-weight: bold;
  color: #aaaaaa;
}
.greypage a:hover {
  color: black;
  transform: scale(2);
}
</style>
