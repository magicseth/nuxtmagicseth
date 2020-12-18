<template>
  <div style="background-color:#333333">
    <div class="header">
      <menu-header />
    </div>
    <div class="maincontent ">
      <div class="title">Welcome</div>
      <p>
        Nunc sagittis enim sed turpis blandit accumsan. Donec porta elementum
        nulla, sollicitudin pharetra ipsum tincidunt id. Aliquam sit amet lacus
        ipsum. Sed eget consectetur orci. Etiam diam massa, ullamcorper at
        blandit dignissim, mollis nec dolor. Fusce malesuada aliquam massa, ac
        dapibus leo laoreet ut. Donec eu nibh condimentum, iaculis lorem vitae,
        gravida nibh. Cras lobortis, nisl accumsan tempus tincidunt, orci diam
        vestibulum nisl, ut consectetur sem nisi eget risus. Morbi maximus purus
        a ligula commodo cursus.
        <br />
        <br />
      </p>

      <p>
        Nullam placerat nunc ante, nec rhoncus nisi sodales eleifend. Vestibulum
        ac neque et nibh hendrerit euismod at ultricies nibh. Aliquam sed
        sodales sem. Integer eu risus blandit, ultrices felis quis, dictum
        augue. Suspendisse non enim iaculis, semper quam quis, sagittis metus.
        In ut massa blandit, dignissim erat et, scelerisque arcu. Morbi vel dui
        ac nibh viverra blandit vel eget ex. Nullam congue mattis est, interdum
        pulvinar quam iaculis ac. Sed congue auctor dolor, sed efficitur tortor
        pulvinar a. Aliquam molestie lacus velit, non dapibus nisl dignissim a.
        Phasellus nisi orci, vehicula pellentesque bibendum nec, pretium eget
        orci.
      </p>
      <br />
      <br />

      <p>
        Aliquam sem quam, faucibus ut purus sit amet, sagittis lacinia quam.
        Pellentesque consequat, neque nec congue vehicula, orci nisl mattis
        massa, eget molestie lectus turpis eget metus. Nunc varius nunc sed sem
        malesuada, eu tincidunt mauris lacinia. Etiam et venenatis mi. Integer
        vel sapien tortor. In elementum eu turpis at vulputate. Nunc maximus
        rhoncus facilisis.
      </p>
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
