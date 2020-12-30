<template>
  <div style="background-color:#333333">
    <div class="header">
      <menu-header />
    </div>
    <div class="maincontent ">
      <div class="title">Seth Raphael</div>
      <p>
        There's a reason companies like Disney, and Google turn to Seth when
        they want to do the impossible.
        <br />
        <br />
        He works with teams small or large to change the way they approach
        technology and product development. Bringing his insights from the world
        of magic he will change what you believe is possible.
        <br />
        <br />
        He is available for performances and workshops.
        <br />
        <a href="mailto:hire@magicseth.com">hire@magicseth.com</a>
      </p>

      <p></p>
    </div>
  </div>
</template>
<script lang="ts">
import Vue from "vue";

export default Vue.extend({
  layout: "greypage",
  //   transition: "impossible",
});
</script>
<style scoped>
* {
  color: white;
}
.fullwidth {
  text-align: left;
  overflow: scroll;
}
p {
  font-size: 1.3em;
  line-height: 1.4em;
  max-width: 800px;
}
.title {
  font-family: "rift_softregular";
  font-size: 8vh;
  padding-bottom: 8vh;
}

.maincontent {
  background-color: #333333;
  /* width: 100vw; */
  margin-left: 12vw;
  margin-right: 12vw;
  /* text-align: center; */
  padding-top: 10vh;
}
</style>
