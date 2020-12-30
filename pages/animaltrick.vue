<template>
  <div>
    <div class="fullgrid">
      <!-- <div class="sideblob">
        <div class="sideblobtext">Animal <br />Trick</div>
      </div> -->
      <div v-if="production != 'development'">
        WHY ARE WESHOIWING THIS
        <img
          src="https://us-central1-numerology.cloudfunctions.net/startAnimal"
          width="0"
          height="0"
        />
      </div>
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
        <div
          class="fullpage clickable centerer"
          @click="
            hideme($event);
            showGoOffline();
          "
        >
          <div class="centerer" style="align-content:end;">
            <div class=" centered title " style="color:#ffffff;font-size:6vw">
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
              style="color:#ffffff;font-size:5vw"
            >
              Okay!
            </div>
          </div>
        </div>
        <div
          class="fullpage centerer onlineonly waiting"
          ref="gooffline"
          @click="hideme"
        >
          <div class="centerer" style="align-content:end">
            <div class="title2  centered" style="font-size:5vw !important">
              to make this
              <div class="title2  centered" style="font-size:8vw !important">
                impossible
              </div>
            </div>
          </div>
          <div class="centerer waiting1">
            <div class="imaginationblob centered" style="width:50vw">
              <imagination-blob class="blobbg" />
            </div>

            <div class="title2  centered">
              let's go offline
            </div>
          </div>
          <div class="centerer" style="align-content:start">
            <div
              class="title2  centered waiting2"
              style="font-size:2em !important"
            >
              Turn on airplane mode<br /><br />
              Turn off Wifi<br /><br />
              Unplug your cables<br /><br />
            </div>
          </div>
        </div>
        <div
          class="fullpage clickable centerer"
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

        <div
          class="fullpage clickable centerer"
          @click="
            hideme($event);
            focusInput();
          "
        >
          <div class="title1 centered" style="align-self:end">
            I need a new pet
          </div>
          <div class="centerer" style="align-self:start">
            <div class="imaginationblob centered" style="width:60vw">
              <imagination-blob class="blobbg" />
            </div>
            <div class="title2  centered">
              Something Unique
            </div>
          </div>
        </div>
        <div class="fullpage centerer" ref="animalsubmission">
          <div class="title2  centered">
            What animal should I get?<br />
            <input
              v-model="input"
              ref="animalinput"
              placeholder="Type your suggestion here"
              @keyup.enter="submitanimal"
            /><br />
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
        <div class="fullpage centerer">
          <div class="title1  centered" style="font-size:10vw">
            {{
              " (" +
                phoneNumber.slice(1, 4) +
                ") " +
                phoneNumber.slice(4, 7) +
                "-" +
                phoneNumber.slice(7, 11)
            }}

            <div class="title1 centered" style="margin-top:5vh;font-size:5vw">
              Now call me, <br />
              But don't ruin the surprise!
            </div>
          </div>
        </div>
      </div>
    </div>
  </div>
</template>

<script lang="ts">
import Vue from "vue";
import CircleBlob from "~/components/CircleBlob.vue";
import animals from "../animal.js";

export default Vue.extend({
  layout: "greypage",
  components: { CircleBlob },
  data() {
    return {
      offline: false,
      bunnynumber: 20,
      hiddenBunnies: "hiddenbunnies",
      bunnyInterval: setInterval(() => {}, 10000),
      input: "",
      phoneNumber: "",
      production: "",
    };
  },
  methods: {
    focusInput() {
      setTimeout(() => {
        (<HTMLElement>this.$refs.animalinput).focus();
      }, 1500);
    },
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
    showGoOffline() {
      (<Element>this.$refs.gooffline).classList.remove("waiting");
    },
    hideme(e: any) {
      console.log(e.currentTarget);
      e.currentTarget.classList.add("hidden");
      //   this.startBunnies();
    },
    submitanimal() {
      if (this.checkAnimal()) {
        (<Element>this.$refs.animalsubmission).classList.add("hidden");
      } else {
        (<HTMLElement>this.$refs.notananimal).style.display = "block";
      }
    },
    checkOffline() {
      if (navigator.onLine) {
        document.body.classList.remove("offline");
      } else {
        document.body.classList.add("offline");
      }
    },
    scrollToBotton() {
      window.scrollTo({
        left: 0,
        top: document.body.scrollHeight,
        behavior: "smooth",
      });
    },
    checkAnimal() {
      let input = this.input;
      input = input.toLowerCase();
      let result = "";
      var words = input.split(" ");
      var lastword = words[words.length - 1];
      const myanimals: { [unit: string]: string } = <
        { [unit: string]: string }
      >(<unknown>animals);
      if (myanimals[input]) {
        result = myanimals[input];
      } else if (myanimals[lastword]) {
        result = myanimals[lastword];
      } else {
        // eslint-disable-next-line
        console.log("failed " + input);
        return false;
      }
      console.log(result);
      this.phoneNumber = result;
      return true;
    },
  },
  mounted() {
    this.production = process.env.NODE_ENV || "";
    console.log(process.env);
    // this.msg.push(Object.keys(animals)[0]);
    window.addEventListener("online", this.checkOffline);
    window.addEventListener("offline", this.checkOffline);
    this.checkOffline();

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
.waiting1 {
  transition: 2s;
  transition-delay: 2.5s;
}
.waiting2 {
  transition: 2s;
  transition-delay: 5s;
}

.waiting .waiting1,
.waiting .waiting2 {
  opacity: 0;
}

.offline .waiting1,
.offline .waiting2 {
  transition: 0s;
  transition-delay: 0s;
}
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
  transition: height 1s ease, opacity 0.5s, margin 1s, visibility 0s ease 1s;
}
.fullpage.clickable {
  cursor: pointer;
}
.fullpage.hidden,
.offline .onlineonly {
  height: 0px;
  opacity: 0;
  overflow: visible;
  visibility: hidden;
}
.imaginationblob {
  transition: 1s;
  width: 70vw;
}

.showoffline {
  opacity: 0;
  display: none;
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
