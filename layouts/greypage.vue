<template>
  <div class="greypage">
    <transition name="layout" mode="out-in">
      <Nuxt />
    </transition>
  </div>
</template>
<style scoped>
.greypage {
  background-color: #333333;
}
</style>
