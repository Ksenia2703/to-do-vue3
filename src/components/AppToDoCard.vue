<template>
  <div class="app-container" id="taskList">
    <h1 class="app-header">TO DO LIST</h1>
    <app-add-task
        v-on:name-tasks="addNewTask"
        :tasksOll="tasks">

    </app-add-task>

    <app-new-task-text
        :tasks="tasks"
        v-on:del-tasks="delTask">

    </app-new-task-text>

  </div>
</template>

<script>
import AppAddTask from "./AppAddTask";
import AppNewTaskText from "./AppNewTaskText";

export default {
  name: "AppToDoCard",
  components: {AppAddTask, AppNewTaskText},
  data() {
    return {
      tasks: [
        { name: 'Start a new pen',},
        { name: 'Read a book'},
        { name: 'Meeting with team'}
      ]
    }
  },
  methods: {
    addNewTask(data) {
      this.tasks.push(data)
    },
    delTask(task) {
      this.tasks.splice(this.tasks.indexOf(task), 1)
    }
  }
}
</script>

<style>
input { outline: none; }

ul {
  list-style: none;
  padding: 0;
}

.app-container {
  border-radius: 8px;
  width: 100%;
  min-width: 300px;
  max-width: 480px;
  max-height: 100%;
  background-color: #10101d;
  padding: 24px;
  overflow: hidden;
}

.app-header {
  font-size: 20px;
  line-height: 32px;
  margin: 0 0 12px 0;
  color: #fff;
}

input {
  width: 16px;
  height: 16px;
  border-radius: 50%;
  border: 1px solid #fff;
  background-image: url("data:image/svg+xml,%3Csvg xmlns='http://www.w3.org/2000/svg' width='24' height='24' viewBox='0 0 24 24' fill='none' stroke-width='2' stroke-linecap='round' stroke-linejoin='round' class='feather feather-check' stroke='%23fff'%3E%3Cpolyline points='20 6 9 17 4 12'/%3E%3C/svg%3E");
  background-repeat: no-repeat;
  background-position: center;
  background-size: 0;
  transition: .2s;
  margin-right: 8px;
  flex-shrink: 0;
  margin-top: 4px;
  appearance: none;}

@supports(-webkit-appearance: none) or (-moz-appearance: none) {
  input[type='checkbox'],
  input[type='radio'] {
    -webkit-appearance: none;
    -moz-appearance: none;
  }
}
</style>