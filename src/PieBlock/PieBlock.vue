<template>
  <div class="pie" :style="`--p: 100; --c: ${props.bg}`">
    <div class="pie animate" :style="`--p: ${props.percent}; --c: ${props.color}`">
      <slot />
    </div>
  </div>
</template>

<script setup>
const props = defineProps({
  bg: {
    type: String,
    required: true
  },
  color: {
    type: String,
    required: true
  },
  percent: {
    type: Number,
    required: true
  }
})
</script>

<style src="./PieBlock.css"></style> <!--Подключение css для круговых диаграм -->
