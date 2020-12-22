<template>
  <div
    @click="bunnynumber++"
    style="position:absolute;left:0px;width:100vw;display:flex;justify-content:space-around;bottom:50vh"
  >
    <img class="bunny1" src="~assets/images/Bunny1.svg" />
    <img class="bunny2" src="~assets/images/Bunny2.svg" />
    <img class="bunny3" src="~assets/images/Bunny3.svg" />
    <img class="bunny4" src="~assets/images/Bunny4.svg" />
    <div style="position:relative">
      <img
        class="bunny5"
        src="~assets/images/Bunny5.svg"
        style="transition:0s"
      />
      <img
        class="bunny6"
        src="~assets/images/Bunny6.svg"
        style="position:absolute;bottom:0;left:0;transition:0s"
      />
      <img
        class="bunny7"
        src="~assets/images/Bunny7.svg"
        style="position:absolute;bottom:0;left:-8%;transition:0s"
      />
      <img
        class="bunny8"
        src="~assets/images/Bunny8.svg"
        style="position:absolute;bottom:0;left:-30%;transition:0s"
      />
      <img
        class="bunny9"
        src="~assets/images/Bunny9.svg"
        style="position:absolute;bottom:0;left:0;transition:0s"
      />
      <img
        class="bunny10"
        src="~assets/images/Bunny10.svg"
        style="position:absolute;bottom:0;left:0"
      />
    </div>
    <img class="bunny11" src="~assets/images/Bunny11.svg" />
    <img class="bunny12" src="~assets/images/Bunny12.svg" />
    <img class="bunny13" src="~assets/images/Bunny13.svg" />
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
  transition: 0.5s ease-out;
  transform: scale(1.5);
}
.showbunny1 .bunny1,
.showbunny2 .bunny2,
.showbunny3 .bunny3,
.showbunny4 .bunny4,
.showbunny5 .bunny5,
.showbunny6 .bunny6,
.showbunny7 .bunny7,
.showbunny8 .bunny8,
.showbunny9 .bunny9,
.showbunny10 .bunny10,
.showbunny11 .bunny11,
.showbunny12 .bunny12,
.showbunny13 .bunny13 {
  /* background-color: red; */
  opacity: 1;
  transition: 0s ease-out;
}
</style>
