<template>
  <div>
    <!--Edit notes starts here-->
    <div
      v-if="editInput"
      class="flex flex-row items-center h-16 bg-white w-full"
    >
      <div class="flex-grow">
        <div class="relative w-full">
          <input
            v-model="selectedNote"
            type="text"
            class="flex w-full border rounded-lg focus:outline-none border-gray-300 focus:border-indigo-300 h-10"
            placeholder="Enter note"
          />
        </div>
      </div>
      <div class="ml-4">
        <!--Update button-->
        <button
          class="flex items-center justify-center bg-indigo-600 hover:bg-indigo-500 rounded-lg text-white p-2 px-3 flex-shrink-0"
          @click="editNote(selectedNote), (editInput = false)"
        >
          Update
        </button>
      </div>
    </div>
    <!--Edit notes ends here-->
  </div>
</template>
<script setup lang="ts">
const props = defineProps({
  note: { type: String, required: true }, // Edited note
});
const selectedNote = ref(props.note.note);
// Close input after editing
const editInput = ref("true");
const emit = defineEmits(["edit"]);
const editNote = (data: any) => {
  emit("edit", { uid: props.note.uid, note: data });
  // Empty the note value
  selectedNote.value = "";
};
</script>
