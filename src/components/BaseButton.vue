<script setup lang="ts">
import { computed } from "vue";
type BaseButtonProps = {
  size?: number;
  color?: string;
};

const props = withDefaults(defineProps<BaseButtonProps>(), {
  size: 16,
  color: "skyblue",
});

const fontSize = computed(() => `${props.size}px`);
</script>

<template>
  <button id="baseButton" :style="{ fontSize, backgroundColor: color }">
    <slot />
  </button>
</template>

<style>
#baseButton {
  padding: 1rem 2rem;
  cursor: pointer;
  border: none;
}
</style>
