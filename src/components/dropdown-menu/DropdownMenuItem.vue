<template>
  <div v-if="props.item.label">
    <ShadcnDropdownMenuItem :disabled="!props.item.clickAction || props.item.clickAction == '' || props.item.disabled">
      <Action :actionClick="props.item.clickAction || ''" class="flex justify-between items-center w-full">
        <div class="flex items-center gap-2">
          <Icon v-if="props.item.iconProps" v-bind="props.item.iconProps" />
          <span>{{ props.item.label }}</span>
        </div>
        <ShadcnDropdownMenuShortcut v-if="props.item.shortcut" class="ml-10">
          {{ props.item.shortcut }}
        </ShadcnDropdownMenuShortcut>
      </Action>
    </ShadcnDropdownMenuItem>
  </div>
</template>

<script setup lang="ts">
import { Icon, Action } from '@geonative/ui/components';
import {
  DropdownMenuItem as ShadcnDropdownMenuItem,
  DropdownMenuShortcut as ShadcnDropdownMenuShortcut,
} from '@geonative/ui/shadcn/ui/dropdown-menu';
import type { DropdownMenuItemType } from '@geonative/ui/types';

const props = defineProps<{
  item: DropdownMenuItemType;
}>();
</script>
