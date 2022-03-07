<template>
  <div class="ba-line">
    <svg width="100%" height="1">
      <line x1="0" y1="0" x2="100%" y2="0" :stroke="color"/>
    </svg>
  </div>
</template>

<script>
export default {
  name: "BaLine",
  props: {
    color: {
      type: String,
      default: '#a2a2a2'
    }
  }
}
</script>
