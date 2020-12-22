<template>
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
  methods: {},
});
</script>
<style scoped>
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

@media only screen and (max-width: 600px) {
  div.sideblob {
    position: absolute;
    height: 40vh;
    bottom: -10vh;
    top: initial;
  }
  div.sideblob * {
    margin-bottom: -10vh;
  }

  .layout-leave-to .realblob {
    transform: scale(10) !important;
  }
}
.sideblob {
  position: absolute;
  right: 0px;
  height: 40vh;
  top: 30vh;
  transition: 0.4s;
}

.sideblob:hover {
  transform: scale(1.2);
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
  transition: 0.4s;
}

.realblob {
  transition: var(--layout-transition-time);
}
.layout-leave-to .realblob {
  transform: scale(19) !important;
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

@media only screen and (max-width: 750px) {
  .imaginationblob:hover .blobbg {
    transform: scale(12);
  }
  .imaginationblob:hover .light {
    transform: scale(1.5);
    opacity: 1;
  }
}
</style>
