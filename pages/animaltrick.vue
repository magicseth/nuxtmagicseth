<template>
  <div>
    <div class="fullgrid" style="position:fixed;top:0px">
      <div class="sideblob">
        <div class="sideblobtext">Animal <br />Trick</div>
      </div>

      <div class="header">
        <menu-header />
        <bunnies-accross :class="'bunny' + bunnynumber" />
      </div>
    </div>
    <div
      class="fullwidth "
      :class="{ offline: offline }"
      style="margin-top:10vh"
    >
      <div style="position:relative">
        <div class="imaginationblob">
          <imagination-blob class="blobbg" />
        </div>
        <div class="title1" @click="offline = !offline">I need a new pet</div>
        <div
          class="title hideoffline"
          style="margin-top:23vh;color:#ffffff;font-size:2em"
        >
          But let's keep this private. <br /><br />
          Turn on airplane mode. Turn off WiFi.
        </div>
        <div class="title2 showoffline" style="margin-top:20vh">
          But what to get?
        </div>
        <div class="title2 showoffline" id="unique" style="margin-top:100vh">
          Something unique...
        </div>
        <div class="title2 showoffline" style="margin-top:100vh">
          What should I get?<br />
          <input
            style="width:50vw;font-size:2vw; border: 1px solid white;
  border-radius: 8px;
  background: transparent"
            @focus="scrollToBotton()"
            placeholder="Type your suggestion here"
          />
        </div>

        <div
          class="title2 showoffline"
          style="margin-top:50vh; height:2.5vw;overflow:hidden"
        >
          (617) 710-7496
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
  data() {
    return {
      offline: false,
      bunnynumber: 0,
    };
  },
  methods: {
    scrollToBotton() {
      window.scrollTo({
        left: 0,
        top: document.body.scrollHeight,
        behavior: "smooth",
      });
    },
  },
  mounted() {
    if (process.client) {
      var mythis = this;
      document.addEventListener(
        "scroll",
        (evt) => {
          var unique = document.getElementById("unique");
          if (unique) {
            var bottom = unique.getBoundingClientRect().bottom;
            var h = window.innerHeight;
            if (bottom < h) {
              var n = Math.floor(((h - bottom) / h) * 12) + 1;
              console.log("n is " + n);
              this.bunnynumber = n;
            } else {
              this.bunnynumber = 0;
            }
          }
        },
        {
          capture: false,
          passive: true,
        }
      );
    }
  },
});
</script>

<style scoped>
.imaginationblob {
  transition: 1s;
}
.offline .imaginationblob {
  opacity: 0;
}
.offline .showoffline {
  opacity: 1;
  display: block;
}
.showoffline {
  opacity: 0;
  display: none;
}
.offline .title1 {
  transition: 1s;
  margin-top: -70vh;
}
.hideoffline {
  transition: 1s;
}
.offline .hideoffline {
  opacity: 0;
}
input[value$="i"] {
  background-color: blue;
}
.fullwidth {
  background-color: teal;
  /* width: 100vw; */
  margin-left: 12vw;
  margin-right: 12vw;
  text-align: center;
}
.title1,
.title2,
.title {
  font-family: "rift_softregular";
  font-size: 10vw;
  width: 75vw;
  color: white;
  text-align: center;
}
.title2 {
  font-size: 7vw !important;
}
.title1 {
  margin-top: -23vw;
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
