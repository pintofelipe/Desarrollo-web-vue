<script setup>
import { ref } from 'vue'

let newTask = ref('')
let taskList = ref([
  { Text: 'Estudiar', done: false },
  { Text: 'Jugar Play', done: true }
])

function addTask() {
  if (newTask.value.trim() === '') return {}

  taskList.value.push({
    Text: newTask.value,
    done: false
  })

  newTask.value = ''


}

function setDone(index){
  taskList.value[index].done = !taskList.value[index].done
  
}

function deleteTask(index){
  taskList.value.splice(index,1)

}



</script>

<template>
  <div class="card">
    <h1>To-Do List</h1>
    <p class="subtitle">{{ newTask }}</p>
    <div>
      <div v-for="(task, index) in taskList" :key="index" class="task" :class="{done: task.done }">
        {{ task.Text }} <span @click="setDone(index)"  @dblclick="deleteTask(index)" class="button">x</span>
      </div>
    </div>
    <div>
      <input
        v-model="newTask"
        @keypress.enter="addTask"
        type="text"
        placeholder="Escribe tu tarea"
      />
      <p class="help" v-show="newTask != ''">presiona "enter" para confirmar</p>
    </div>
  </div>
</template>

<style scoped>
.done {
  text-decoration: line-through;
 
}
.help {
  margin: 0;
  font-size: 10px;
  opacity: 0.4;
}

.task {
  display: flex;
  background-color: #8f6593;
  border-radius: 4px;
  padding: 2px 8px;
  padding-right: 2px;
  margin-bottom: 2px;
  justify-content: space-between;
}
.task:hover {
  background-color: #aea4bf;
}

.button {
  display: inline-flex;
  align-items: center;
  background-color: #3b252c;
  padding: 0 5px;
  border-radius: 2px;
  color: white;
  /* font-size: 14px; */
  /* line-height: 14px; */
  /* height: 16px; */
}

h1 {
  text-transform: uppercase;
  text-align: center;
  padding: 0;
  margin: 0;
  font-size: 24px;
}

input {
  width: 100%;
  box-sizing: border-box;
  border: none;
  outline: none;
  padding: 3px 6px;
  border-radius: 4px;
}

.card {
  font-family: 'Ubuntu', sans-serif;
  background-color: #cdcdcd;
  max-width: 520px;
  border-radius: 8px;
  padding: 18px 16px;
  margin: 0 auto;
}

.subtitle {
  padding: 0;
  margin: 0;
  text-align: center;
  opacity: 0.6;
  margin-bottom: 16px;
}

.button:hover {
  cursor: pointer;
  background-color: aliceblue;
  color: #8f6593;
}
</style>
