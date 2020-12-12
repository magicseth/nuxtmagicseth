<template>
  <div>
    <div class="fullgrid">
      <div class="header">
        <menu />
      </div>
      <quotes-bg />

      <transition name="layout" mode="out-in">
        <Nuxt />
      </transition>

      <resume-footer />
    </div>
  </div>
</template>
