<template>
  <div>
    <div class="flex">
      <img
        class="h-10 w-10 flex-shrink-0 rounded-full bg-gray-300"
        src="https://cdn-icons-png.flaticon.com/128/847/847969.png"
        alt=""
      />
      <div class="flex">
        <p class="ml-3">Sita</p>

        <PencilIcon
          class="h-5 w-4 sm:ml-[12px] sm:mb-[-20px] right-0"
          @click="emitData(note, 'edit')"
        />
        <TrashIcon
          class="h-5 w-4 sm:ml-[10px] sm:mb-[-20px] right-0"
          @click="emitData(note, 'delete')"
        />
      </div>
    </div>
    <span class="ml-[52px] text-gray-600">{{ note.note }}</span>
  </div>
</template>

<script setup lang="ts">
import { PencilIcon, TrashIcon } from "@heroicons/vue/24/outline";
const emit = defineEmits(["emitData"]);
const props = defineProps({
  note: { type: Object, required: true },
  index: { type: Number, required: true },
});

const emitData = (note: any, value: any) => {
  emit("emitData", { note: note, value: value, index: props.index });
};
</script>
