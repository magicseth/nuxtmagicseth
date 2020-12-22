<template>
  <div class="main" style="min-width: 20vh; min-height: 20vh">
    <circle-blob style="position: absolute" />
    <enter-blob
      class="enterblob"
      style="  width: calc(100px / 100vw);
  height: calc(100px / 100vw);
"
    />
    <div class="blobtext">
      Let me open<br />
      your mind.<br /><nuxt-link to="impossible">
        <span class="button" style=""> ENTER</span></nuxt-link
      >
    </div>
  </div>
</template>

<script lang="ts">
import Vue from "vue";
import CircleBlob from "~/components/CircleBlob.vue";

export default Vue.extend({
  layout: "home",
  components: { CircleBlob },
  head: {
    bodyAttrs: {
      class: "impossible",
    },
  },
});
</script>

<style>
.blobtext a {
  color: #333333;
  text-decoration: none !important;
}
.enterblob {
  transform: scale(0.2);
  transition: transform 0.3s;
  transition-timing-function: ease-out;
  /* opacity: 0; */
}
.blobtext {
  /* display: none; */
  position: absolute;
  width: 400px;
  height: 400px;
  padding-top: 40%;
  left: calc(-200px + 50%);
  top: -50%;
  font-size: 8vh;
  font-family: "rift_softregular";
  color: #333333;
  text-align: center;
  /* opacity: 0; */
  transform: scale(0);
  transition: 0.3s;
  transition-timing-function: ease-out;
}
.main:hover .enterblob {
  transform: scale(3);
  opacity: 1;
}

/* .layout-leave {} */
.layout-leave-active .enterblob {
  transition: 1s;
}
.layout-leave-to .enterblob {
  transform: scale(20) !important;
}

.layout-leave-active .blobtext {
  opacity: 0 !important;
}

.main:hover .blobtext,
.blobtext2 {
  display: block;
  opacity: 1;
  transform: scale(1);
}

.button {
  border: 2px solid #333333;
  border-radius: 30px;
  font-size: 2.3vh;
  padding: 7px 40px 7px 40px;
}
</style>
