<template>
  <div>
    <PencilIcon
      class="h-5 w-5 sm:ml-[227px] sm:mb-[-21px] right-0"
      @click="emit('emitData', { tag: tag, value: 'edit', index: props.index })"
    />
    <TrashIcon
      class="h-5 w-5 sm:ml-[260px] sm:mb-[-21px] right-0"
      @click="
        emit('emitData', { tag: tag, value: 'delete', index: props.index })
      "
    />
  </div>
  <div class="relative mt-8 flex items-center gap-x-4">
    <div class="text-sm leading-6 group">
      <span class="text-gray-600">{{ tag.name }}</span>
    </div>
  </div>
</template>

<script setup lang="ts">
import { PencilIcon, TrashIcon } from "@heroicons/vue/24/outline";
const emit = defineEmits(["emitData"]);
const props = defineProps({
  tag: { type: Object, required: true },
  index: { type: Number, required: true },
});
</script>
