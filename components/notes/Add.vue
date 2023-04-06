<template>
  <div>
    <!--Add Note starts here-->
    <div class="flex flex-row items-center px-4 bottom-0px position:fixed">
      <div class="flex-grow ml-4">
        <input
          v-model="note"
          placeholder="Enter Note"
          type="text"
          class="flex w-[335px] border rounded-xl focus:outline-none focus:border-indigo-300 pl-4 h-10"
        />
      </div>
      <div class="ml-4">
        <!--Send button-->
        <button
          class="flex items-center justify-center bg-indigo-500 hover:bg-indigo-600 rounded-lg text-white px-4 py-1.5 flex-shrink-0"
          @click="saveNote"
        >
          Add
        </button>
      </div>
      <!--Add Note ends here-->
    </div>
  </div>
</template>
<script setup lang="ts">
const note = ref("");
const emit = defineEmits(["add"]);
const saveNote = () => {
  // Emit note added
  emit("add", note.value);
  // Empty note value after adding the note
  note.value = "";
};
</script>
