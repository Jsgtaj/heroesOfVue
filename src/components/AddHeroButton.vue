<script>
export default {
  name: "add-hero-button",
  props: ["btn-txt"]
}
</script>
<template>
  <a @click="$emit('add-hero', true)" class="f6 link dim br3 ba ph3 pv2 mb2 mt2 dib dark-gray" href="#0">
    {{ btnTxt }}
  </a>
</template>