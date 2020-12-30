<template>
  <div class="greypage">
    <transition name="layout" mode="out-in">
      <Nuxt />
    </transition>
  </div>
</template>
<style>
.greypage {
  background-color: #333333;
}
html {
  background-color: #333333;
  min-height: 100%;
}
</style>
