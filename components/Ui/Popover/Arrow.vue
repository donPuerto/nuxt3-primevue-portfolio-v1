<script lang="ts" setup>
import { PopoverArrow, useForwardProps } from 'radix-vue';
import type { PopoverArrowProps } from 'radix-vue';

const props = withDefaults(defineProps<PopoverArrowProps>(), {
  width: 10,
  height: 5,
});

const forwarded = useForwardProps(props);
</script>

<template>
  <PopoverArrow v-bind="forwarded" />
</template>
