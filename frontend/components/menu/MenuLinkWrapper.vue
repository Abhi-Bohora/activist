<!-- SPDX-License-Identifier: AGPL-3.0-or-later -->
<template>
  <NuxtLink
    class="font-md focus-brand group relative flex w-full basis-full items-center justify-center rounded-md text-left text-sm transition duration-200"
    :class="{
      'style-menu-option-cta': selected,
      'style-menu-option': !selected && isAddStyles,
      'p-2': isAddStyles,
    }"
    :to="localePath(`${to}`)"
  >
    <slot />
  </NuxtLink>
</template>

<script setup lang="ts">
const localePath = useLocalePath();

export interface Props {
  to: string;
  selected: boolean;
  isAddStyles?: boolean;
}

withDefaults(defineProps<Props>(), {
  isAddStyles: true,
});
</script>
