<template>
  <div
    @click="bunnynumber++"
    style="position:absolute;left:0px;width:100vw;display:flex;justify-content:space-around;bottom:1vh"
  >
    <img src="~assets/images/Bunny1.svg" />
    <img src="~assets/images/Bunny2.svg" />
    <img src="~assets/images/Bunny3.svg" />
    <img src="~assets/images/Bunny4.svg" />
    <img src="~assets/images/Bunny5.svg" />
    <img src="~assets/images/Bunny6.svg" />
    <img src="~assets/images/Bunny7.svg" />
    <img src="~assets/images/Bunny8.svg" />
    <img src="~assets/images/Bunny9.svg" />
    <img src="~assets/images/Bunny10.svg" />
    <img src="~assets/images/Bunny11.svg" />
    <img src="~assets/images/Bunny12.svg" />
    <img src="~assets/images/Bunny13.svg" />
  </div>
</template>
<script lang="ts">
import Vue from "vue";
export default Vue.extend({
  data() {
    return {
      bunnynumber: 0,
    };
  },
});
</script>

<style scoped>
div {
  align-items: flex-end;
}
img {
  opacity: 0;
  transition: 1.2s ease-out;
}
.bunny1 img:nth-child(1),
.bunny2 img:nth-child(2),
.bunny3 img:nth-child(3),
.bunny4 img:nth-child(4),
.bunny5 img:nth-child(5),
.bunny6 img:nth-child(6),
.bunny7 img:nth-child(7),
.bunny8 img:nth-child(8),
.bunny9 img:nth-child(9),
.bunny10 img:nth-child(10),
.bunny11 img:nth-child(11),
.bunny12 img:nth-child(12),
.bunny13 img:nth-child(13) {
  /* background-color: red; */
  opacity: 1;
  transition: 0s ease-out;
}
</style>
