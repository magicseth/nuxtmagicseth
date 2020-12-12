<template>
  <div class="footer">
    <div>Seth Raphael</div>
    <div class="footerLinks">
      <div>TED Fellow</div>
      <static-circle width="2.5vh" height="2.5vh" />
      <div>Parent of 5</div>
      <static-circle width="2.5vh" height="2.5vh" />

      <div>Inventor at Google</div>
      <static-circle width="2.5vh" height="2.5vh" />
      <div>Degree in wonder from MIT</div>
    </div>
  </div>
</template>
<style>
.footer div {
  align-self: center;
}
.footerLinks {
  align-self: center;

  display: flex;
  justify-content: space-evenly;
  font-size: 2vw;
}
.footerLinks svg {
  opacity: 0.3;
}
</style>
