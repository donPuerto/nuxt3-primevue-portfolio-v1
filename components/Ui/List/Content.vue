<script lang="ts" setup>
import { Primitive } from 'radix-vue';
import type { PrimitiveProps } from 'radix-vue';

const props = withDefaults(
  defineProps<
      PrimitiveProps & {
        /** Custom class(es) to add to the parent */
        class?: any;
      }
    >(),
  {
    as: 'div',
  },
);
const forwarded = reactiveOmit(props, 'class');
const styles = tv({
  base: 'flex flex-col gap-1 leading-none',
});
</script>

<template>
  <Primitive :class="styles({ class: props.class })" v-bind="forwarded">
    <slot />
  </Primitive>
</template>
