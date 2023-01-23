<script setup>
import { ref } from "vue"
import { v4 as uuidv4 } from 'uuid';
const body = document.getElementById("body")
const showModal = ref(false)
const newNoteTitle = ref("")
const newNote = ref("")
const errorMessage = ref("")

const getRandomColor = () => {
  let color = "hsl(" + Math.random() * 360 + ", 100%, 75%)";
  return color;
}

const notes = ref([
  {
    id: "3a73ea12-3e49-4d10-95e5-2e1fe9a7f110",
    title: "Note Title",
    text: "Lorem ipsum dolor sit amet, consectetur adipisicing elit. Adipisci, est sed perferendis quos dolor atque ducimus ex eos enim velit?",
    date: new Date("Mon Jan 23 2023 10:37:10 GMT+0330 (Iran Standard Time)"),
    backgroundColor: "hsl(120.51648750742788, 100%, 75%)",
  },
  {
    id: "3a73ea12-3e49-4d10-95e5-2e1fe9a7f110",
    title: "Note Title",
    text: "Lorem ipsum dolor sit amet, consectetur adipisicing elit. Adipisci, est sed perferendis quos dolor atque ducimus ex eos enim velit?",
    date: new Date("Mon Jan 23 2023 10:37:10 GMT+0330 (Iran Standard Time)"),
    backgroundColor: getRandomColor(),
  },
  {
    id: "3a73ea12-3e49-4d10-95e5-2e1fe9a7f110",
    title: "Note Title",
    text: "Lorem ipsum dolor sit amet, consectetur adipisicing elit. Lorem ipsum dolor sit amet, consectetur adipisicing elit. Lorem ipsum dolor sit amet, consectetur adipisicing elit. Lorem ipsum dolor sit amet, consectetur adipisicing elit. Lorem ipsum dolor sit amet, consectetur adipisicing elit. Lorem ipsum dolor sit amet, consectetur adipisicing elit. Lorem ipsum dolor sit amet, consectetur adipisicing elit. Adipisci, est sed perferendis quos dolor atque ducimus ex eos enim velit?",
    date: new Date("Mon Jan 23 2023 10:37:10 GMT+0330 (Iran Standard Time)"),
    backgroundColor: getRandomColor(),
  },
  {
    id: "3a73ea12-3e49-4d10-95e5-2e1fe9a7f110",
    title: "Note Title",
    text: "Lorem ipsum dolor sit amet, consectetur adipisicing elit. Adipisci, est sed perferendis quos dolor atque ducimus ex eos enim velit?",
    date: new Date("Mon Jan 23 2023 10:37:10 GMT+0330 (Iran Standard Time)"),
    backgroundColor: getRandomColor(),
  },
  {
    id: "3a73ea12-3e49-4d10-95e5-2e1fe9a7f110",
    title: "Note Title",
    text: "Lorem ipsum dolor sit amet, consectetur adipisicing elit. Adipisci, est sed perferendis quos dolor atque ducimus ex eos enim velit?",
    date: new Date("Mon Jan 23 2023 10:37:10 GMT+0330 (Iran Standard Time)"),
    backgroundColor: getRandomColor(),
  },
  {
    id: "3a73ea12-3e49-4d10-95e5-2e1fe9a7f110",
    title: "Note Title",
    text: "Lorem ipsum dolor sit amet, consectetur adipisicing elit. Adipisci, est sed perferendis quos dolor atque ducimus ex eos enim velit?",
    date: new Date("Mon Jan 23 2023 10:37:10 GMT+0330 (Iran Standard Time)"),
    backgroundColor: getRandomColor(),
  },
  {
    id: "3a73ea12-3e49-4d10-95e5-2e1fe9a7f110",
    title: "Note Title",
    text: "Lorem ipsum dolor sit amet, consectetur adipisicing elit. Adipisci, est sed perferendis quos dolor atque ducimus ex eos enim velit?",
    date: new Date("Mon Jan 23 2023 10:37:10 GMT+0330 (Iran Standard Time)"),
    backgroundColor: getRandomColor(),
  },
  {
    id: "3a73ea12-3e49-4d10-95e5-2e1fe9a7f110",
    title: "Note Title",
    text: "Lorem ipsum dolor sit amet, consectetur adipisicing elit. Adipisci, est sed perferendis quos dolor atque ducimus ex eos enim velit?",
    date: new Date("Mon Jan 23 2023 10:37:10 GMT+0330 (Iran Standard Time)"),
    backgroundColor: getRandomColor(),
  },
  {
    id: "3a73ea12-3e49-4d10-95e5-2e1fe9a7f110",
    title: "Note Title",
    text: "Lorem ipsum dolor sit amet, consectetur adipisicing elit. Adipisci, est sed perferendis quos dolor atque ducimus ex eos enim velit?",
    date: new Date("Mon Jan 23 2023 10:37:10 GMT+0330 (Iran Standard Time)"),
    backgroundColor: getRandomColor(),
  },
  {
    id: "3a73ea12-3e49-4d10-95e5-2e1fe9a7f110",
    title: "Note Title",
    text: "Lorem ipsum dolor sit amet, consectetur adipisicing elit. Adipisci, est sed perferendis quos dolor atque ducimus ex eos enim velit?",
    date: new Date("Mon Jan 23 2023 10:37:10 GMT+0330 (Iran Standard Time)"),
    backgroundColor: getRandomColor(),
  },
  {
    id: "3a73ea12-3e49-4d10-95e5-2e1fe9a7f110",
    title: "Note Title",
    text: "Lorem ipsum dolor sit amet, consectetur adipisicing elit. Adipisci, est sed perferendis quos dolor atque ducimus ex eos enim velit?",
    date: new Date("Mon Jan 23 2023 10:37:10 GMT+0330 (Iran Standard Time)"),
    backgroundColor: getRandomColor(),
  },
  {
    id: "3a73ea12-3e49-4d10-95e5-2e1fe9a7f110",
    title: "Note Title",
    text: "Lorem ipsum dolor sit amet, consectetur adipisicing elit. Adipisci, est sed perferendis quos dolor atque ducimus ex eos enim velit?",
    date: new Date("Mon Jan 23 2023 10:37:10 GMT+0330 (Iran Standard Time)"),
    backgroundColor: getRandomColor(),
  },
  {
    id: "3a73ea12-3e49-4d10-95e5-2e1fe9a7f110",
    title: "Note Title",
    text: "Lorem ipsum dolor sit amet, consectetur adipisicing elit. Adipisci, est sed perferendis quos dolor atque ducimus ex eos enim velit?",
    date: new Date("Mon Jan 23 2023 10:37:10 GMT+0330 (Iran Standard Time)"),
    backgroundColor: getRandomColor(),
  }
])

console.log(notes)


const toggleModal = () => {
  showModal.value = !showModal.value
  body.classList.toggle("overflow-hidden")
}

const addNote = () => {
  if (newNote.value.length < 10) {
    return errorMessage.value = "To short text. write more..."
  }
  notes.value.push({
    id: uuidv4(),
    title: newNoteTitle.value,
    text: newNote.value,
    date: new Date(),
    backgroundColor: getRandomColor()
  })
  newNoteTitle.value = ""
  newNote.value = ""
  toggleModal()
  errorMessage.value = ""
}


</script>

<template>
  <main>
    <!-- + Overlay -->
    <div class="overlay" v-show="showModal">
      <div class="modal w-[720px] bg-white p-4 rounded-md -mt-32">
        <div class="flex items-center justify-between">
          <h3 class="font-bold">Write a Note:</h3>
          <div class="flex gap-3">
            <button class="text-sm text-slate-500" @click="toggleModal">Discard</button>
            <button class="bg-blue-500 py-2 px-4 rounded-md text-white text-sm" @click="addNote">Add Note</button>
          </div>
        </div>
        <input type="text" maxlength="50"
          class="outline-none text-lg font-bold w-full bg-zinc-100 py-2 px-3 mt-2 rounded-md" placeholder="Title..."
          v-model="newNoteTitle">
        <!-- Text Area -->
        <textarea v-model.lazy.trim="newNote" name="note" id="note" rows="10"
          class="w-full outline-none my-2 border-l-2 border-slate-200 px-3 rounded-sm"
          placeholder="Write here..."></textarea>
        <p v-if="errorMessage" class="font-bold text-xs text-red-500">{{ errorMessage }}</p>
      </div>
    </div>
    <!-- - Overlay -->

    <div class="mt-5 flex items-center justify-between pt-2 pb-4">
      <h1 class="text-5xl font-extrabold text-slate-800">Notes</h1>
      <button
        class="bg-slate-800 hover:bg-slate-900 transition-colors ease-linear duration-100 text-white rounded-full w-10 h-10 flex justify-center items-center"
        @click="toggleModal">
        <svg xmlns="http://www.w3.org/2000/svg" fill="none" viewBox="0 0 24 24" stroke-width="3" stroke="currentColor"
          class="w-4 h-4">
          <path stroke-linecap="round" stroke-linejoin="round" d="M12 4.5v15m7.5-7.5h-15" />
        </svg>
      </button>
    </div>

    <section class=" my-6 grid gap-3 grid-cols-1 md:grid-cols-2 lg:grid-cols-4">

      <!-- + Some Note -->
      <div v-for="note in notes" class="note p-4 w-full bg-green-300 h-64 rounded-md flex flex-col justify-between"
        :style="{ backgroundColor: note.backgroundColor }">
        <div>
          <header>
            <h2 class="font-bold overflow-clip w-full break-words">{{ note.title }}</h2>
          </header>
          <main>
            <p class="note-text text-sm mt-2 overflow-clip w-full break-words h-[10rem] overflow-y-auto pr-1">
              {{ note.text }}
            </p>
          </main>
        </div>

        <footer>
          <span class="text-[11px] opacity-70"> {{ note.date.getHours() }}:{{ note.date.getMinutes() }}:{{
            note.date.getSeconds()
          }} | {{
  note.date.toLocaleDateString("en-US")
}}</span>
        </footer>
      </div>
      <!-- - Some Note -->

    </section>
  </main>
</template>

<style scoped>
.overlay {
  width: 100%;
  height: 100vh;
  position: absolute;
  top: 0;
  left: 0;
  z-index: 100;
  background-color: rgba(0, 0, 0, 0.74);
  display: flex;
  align-items: center;
  justify-content: center;
  overflow: hidden;
}
</style>