ffloat<template>
  <div class="fullgrid">
    <div class="sideblob">
      <side-blob class="realblob" style="height:40vh" />

      <div class="sideblobtext">
        <nuxt-link to="/animaltrick">Animal <br />Trick</nuxt-link>
      </div>
    </div>

    <div class="header">
      <menu-header />
    </div>

    <div class="main">
      <div style="position:relative">
        <div class="title">Let's do the impossible</div>
        <div class="imaginationblob">
          <div class="centerer">
            <imagination-blob class="blobbg centered" />
            <span class="light centered"
              >I'll push what you think is possible <br />
              using technology and your imagination.</span
            >
          </div>
        </div>
      </div>
    </div>
  </div>
</template>
<script lang="ts">
import Vue from "vue";

export default Vue.extend({
  layout: "bluepage",
  //   transition: "impossible",
});
</script>
<style scoped>
.centerer {
  display: grid;
}

.item-a {
  grid-area: header;
}
.item-b {
  grid-area: main;
}
.item-c {
  grid-area: sidebar;
}
.item-d {
  grid-area: footer;
}

.centerer {
  display: grid;
  grid-template-columns: 1fr;
  grid-template-rows: auto;
  grid-template-areas: "thespot";
}

.foot {
  grid-area: thespot;
}

.centered {
  grid-area: thespot;
  place-self: center;
}

@media only screen and (max-width: 600px) {
  div.sideblob {
    position: absolute;
    height: 40vh;
    bottom: 0px;
    top: initial;
  }
  div.sideblob * {
    margin-bottom: -10vh;
  }
}
.sideblob {
  position: absolute;
  right: 0px;
  height: 40vh;
  top: 30vh;
  transition: 0.3s;
}
.sideblob a {
  text-decoration: none;
  color: white;
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

.realblob {
  transition: 0.3s;
}
.layout-leave-active .realblob {
  transition: 0.3s;
}
.layout-leave-to .realblob {
  transform: scale(30) !important;
}

.layout-leave-active .sideblobtext {
  /* right: 100px !important; */
  opacity: 0 !important;
}
.title {
  font-family: "rift_softregular";
  font-size: 8vw;
}
.imaginationblob {
  width: 100%;
  text-align: center;
}
.light {
  color: white;
  font-size: 4vw;
  margin-top: -0.5em;
  font-family: "rift_softregular";
  transform: scale(0.1);
  opacity: 0;
  transition: 0.4s;
}
.blobbg {
  width: 10vw;
}
.imaginationblob .blobbg {
  transition: 0.4s;
}
.imaginationblob:hover .blobbg {
  transform: scale(8);
}
.imaginationblob:hover .light {
  transform: scale(1);
  opacity: 1;
}
</style>
