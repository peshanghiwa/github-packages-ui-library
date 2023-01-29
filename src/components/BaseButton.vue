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
  <button class="base-button">
    <slot />
  </button>
</template>

<style scoped>
.base-button {
  background-color: v-bind(color);
  font-size: v-bind(fontSize);
  padding: 1rem 2rem;
  cursor: pointer;
  border: none;
}
</style>
