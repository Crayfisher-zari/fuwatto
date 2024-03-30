<script lang="ts" setup>
type Props = {
  play?: () => void;
  animation?: (ref: HTMLElement | null) => void;
};
const props = defineProps<Props>();
const element = ref<HTMLElement | null>(null);
onMounted(() => {
  props.animation?.(element.value);
});
</script>
<template>
  <div class="wrapper">
    <div ref="element">
      <p>Fuwatto</p>
    </div>
    <button @click="play">再生</button>
  </div>
</template>
<style lang="scss">
.wrapper {
  width: 240px;
  height: 240px;
  box-shadow: inset 0 0 24px var(--bg);
  border-radius: 16px;
}
</style>
