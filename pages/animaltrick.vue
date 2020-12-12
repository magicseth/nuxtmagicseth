<template>
  <div class="fullgrid">
    <div class="sideblob">
      <div class="sideblobtext">Animal <br />Trick</div>
    </div>

    <div class="header">
      <menu-header />
    </div>

    <div class="main">
      <div style="position:relative">
        <div class="title">I need a new pet</div>
        <div class="imaginationblob">
          <imagination-blob class="blobbg" />
          <span class="light"
            >I'll push what you think is possible <br />
            using technology and your imagination.</span
          >
        </div>
      </div>
    </div>
  </div>
</template>

<script lang="ts">
import Vue from "vue";
import CircleBlob from "~/components/CircleBlob.vue";

export default Vue.extend({
  layout: "greypage",
  components: { CircleBlob },
});
</script>

<style scoped>
.title {
  font-family: "rift_softregular";
  font-size: 10vw;
  color: white;
}
.sideblob {
  position: absolute;
  left: 0px;
  height: 40vh;
  top: 30vh;
  transition: 0.3s;
  width: 10vw;
}
.sideblobtext {
  text-align: right;
  margin: 0;
  position: absolute;
  top: 50%;
  -ms-transform: translateY(-50%);
  transform: translateY(-50%);
  color: white;
  width: 100%;
  padding-right: 20px;
  font-size: 3.5vh;

  font-family: "rift_softregular";
  transition: 0.3s;
}
</style>
