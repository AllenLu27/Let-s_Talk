<!--
  Props:
    fixed
 -->
<template>
  <header
    class="soul-header"
    :class="{'soul-header-fixed': fixed}"
  >
    <div class="soul-header-left">
      <slot name="left">left</slot>
    </div>
    <div class="soul-header-center">
      <slot name="center">middle</slot>
    </div>
    <div class="soul-header-right">
      <slot name="right">right</slot>
    </div>
  </header>
</template>

<script>
export default {
  name: 'SoulBaseHeader',
  props: {
    fixed: {
      type: [Boolean],
      default: false
    }
  }
}
</script>

<style>
.soul-header {
  display: flex;
  justify-content: space-around;
  align-items: center;
  box-shadow:
  0rem
  0.05rem
  var(--box-shadow-blur, 0.35rem)
  var(--box-shadow-color, #D6D6D6);
  height: 1rem;
  transition: 0.5s;
  background-color: var(--background-color, #fff);
  z-index: var(--header, 2);
}
.soul-header-left {
  display: flex;
  justify-content: flex-start;
  align-items: center;
  width: 25%;
}
.soul-header-center {
  display: flex;
  justify-content: center;
  align-items: center;
  width: 30%;
  font-size: var(--font-size-header-center, 0.32rem);
}
.soul-header-right {
  display: flex;
  justify-content: flex-end;
  align-items: center;
  width: 25%;
}
.soul-header-fixed {
  position: fixed;
  top: 0;
  right: 0;
  left: 0;
  z-index: var(--header);
}
</style>
