<script lang="ts" setup>
import { ComboboxGroup } from 'radix-vue';
import type { ComboboxGroupProps } from 'radix-vue';

const props = defineProps<
    ComboboxGroupProps & {
      /**The heading for the group */
      heading?: any;
      /**Custom class(es) to add to the element */
      class?: any;
    }
  >();
const forwarded = reactiveOmit(props, 'class', 'heading');
const styles = tv({
  base: 'overflow-hidden p-1 text-foreground',
});
</script>

<template>
  <ComboboxGroup :class="styles({ class: props.class })" v-bind="forwarded">
    <slot name="heading">
      <UiCommandLabel v-if="heading" :label="heading" />
    </slot>
    <slot />
  </ComboboxGroup>
</template>
