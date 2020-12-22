<template>
  <div>
    <div class="fullgrid">
      <!-- <div class="sideblob">
        <div class="sideblobtext">Animal <br />Trick</div>
      </div> -->

      <div class="header">
        <menu-header />
        <bunnies-accross
          ref="bunnies"
          :class="['showbunny' + bunnynumber, hiddenBunnies]"
        />
      </div>

      <div
        :class="{ offline: offline }"
        class="animaltrick"
        style="place-self:stretch; top:0px; left:0px"
      >
        <div class="fullpage centerer" @click="hideme">
          <div class="centerer" style="align-content:end;">
            <div
              class=" centered title hideoffline"
              style="color:#ffffff;font-size:4em"
            >
              I'd like to read your mind
            </div>
          </div>
          <div class="centerer">
            <div
              class="imaginationblob centered"
              style="width:30vw;cursor:pointer"
            >
              <imagination-blob class="blobbg" />
            </div>
            <div
              class=" centered title hideoffline"
              style="color:#ffffff;font-size:4em"
            >
              Okay!
            </div>
          </div>
        </div>
        <div class="fullpage centerer" @click="hideme">
          <div class="centerer" style="align-content:end">
            <div class="title2  centered" style="font-size:5vw !important">
              to make this
              <div class="title2  centered" style="font-size:8vw !important">
                impossible
              </div>
            </div>
          </div>
          <div class="centerer">
            <div class="imaginationblob centered" style="width:50vw">
              <imagination-blob class="blobbg" />
            </div>

            <div class="title2  centered">
              lets go offline
            </div>
          </div>
          <div class="centerer" style="align-content:start">
            <div class="title2  centered" style="font-size:2em !important">
              Turn on airplane mode<br /><br />
              Turn off Wifi<br /><br />
              Unplug your cables<br /><br />
            </div>
          </div>
        </div>
        <div
          class="fullpage centerer"
          @click="
            hideme($event);
            startBunnies();
          "
        >
          <div class="centerer">
            <div class="imaginationblob centered">
              <imagination-blob class="blobbg" />
            </div>

            <div class="title2  centered">
              My rabbit quit
            </div>
          </div>
        </div>
        <div class="fullpage centerer" ref="bunnyPage"></div>

        <div class="fullpage centerer" @click="hideme">
          <div class="title2 centered" style="align-self:end">
            I need a new pet
          </div>
          <div class="centerer" style="align-self:start">
            <div class="imaginationblob centered" style="width:40vw">
              <imagination-blob class="blobbg" />
            </div>
            <div class="title3  centered">
              Something Unique
            </div>
          </div>
        </div>
        <div class="fullpage centerer">
          <div class="title2  centered">
            What animal should I get?<br />
            <input placeholder="Type your suggestion here" /><br />
            <div
              style=";margin:auto;text-align:right;width:50vw;font-size:max(.7rem, 1.5vw);margin-top:1vw"
            >
              Press enter to commit.
            </div>
            <br />
            <div style="font-size:4rem;display:none" ref="notananimal">
              Hmm, that doesn't seem like an animal to me. <br />Could you Try
              something else?<br />
            </div>
          </div>
        </div>
        <div class="fullpage centerer" @click="hideme">
          <div class="title2  centered">
            (617) 710-7496
          </div>
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
      bunnynumber: 20,
      hiddenBunnies: "",
      bunnyInterval: setInterval(() => {}, 10000),
    };
  },
  methods: {
    startBunnies() {
      this.hiddenBunnies = "";

      this.bunnynumber = 0;
      clearInterval(this.bunnyInterval);
      this.bunnyInterval = setInterval(() => {
        this.bunnynumber++;
        if (this.bunnynumber == 14) {
          console.log(this.$refs.bunnyPage);
          (<Element>this.$refs.bunnyPage).classList.add("hidden");
          this.hiddenBunnies = "hiddenbunnies";

          clearInterval(this.bunnyInterval);
        }
      }, 400);
    },
    hideme(e: any) {
      console.log(e.currentTarget);
      e.currentTarget.classList.add("hidden");
      //   this.startBunnies();
    },
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
.hiddenbunnies {
  display: none !important;
}
.animaltrick {
  grid-column: header/footer;
  grid-row: header / footer;
}

.main {
  height: 100vh;
  overflow: hidden;
}
.fullpage {
  height: 100vh;
  transition: height 1s ease, opacity 1s, margin 1s;
}
.fullpage.hidden {
  height: 0px;
  opacity: 0;
  overflow: hidden;
}
.imaginationblob {
  transition: 1s;
  width: 70vw;
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
  margin-top: -100vh;
}
.hideoffline {
  transition: 1s;
}
.offline .hideoffline {
  opacity: 0;
  margin-top: -100vh;
}
input {
  width: 50vw;
  font-size: max(1.4rem, 3vw);
  border: 1px solid white;
  padding-top: 2px;
  background: transparent;
  border-radius: 3% 3% 3% 15% / 60% 40% 60% 60%;
  color: white;
  font-family: reenie_beanieregular;
  text-align: center;
  text-transform: uppercase;
}
input:focus {
  outline: none;
}
input::-webkit-input-placeholder {
  font-family: rift_softregular;
}
.title1,
.title2,
.title3,
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

.title3 {
  font-size: 5vw !important;
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
