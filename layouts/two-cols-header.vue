<!--
  Usage:
```md
---
layout: two-cols-header
---
This shows up across both
::left::
# Left
This shows on the left
::right::
# Right
This shows on the right
```
-->

<script setup lang="ts">
const props = defineProps({
  class: {
    type: String,
  },
})
</script>

<template>
  <div class="slidev-layout two-columns w-full h-full">
    <div class="col-span-2">
      <slot />
    </div>
    <div class="grid grid-cols-2 grid-rows-2">
      <div class="col-left" :class="props.class">
        <slot name="left" />
      </div>
      <div class="col-right" :class="props.class">
        <slot name="right" />
      </div>
    </div>
  </div>
</template>

<style scoped>
.col-left,
.col-right {
  display: flex;
  flex-direction: column;
  align-items: center;
  justify-content: center;
}

.slidev-layout ul {
  list-style: none !important;
}
</style>