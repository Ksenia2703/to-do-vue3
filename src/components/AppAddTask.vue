<template>
  <div class="add-task">
    <input type="text"
           autocomplete="off"
           placeholder="Add New Task"
           class="task-input"
           v-model.trim="tasks.name">
    <button value=""
            class="submit-task"
            title="Add Task"
            @click.prevent="newItem">
    </button>
  </div>
</template>

<script>
export default {
  name: "AppAddTask",
  data() {
    return {
      tasks: []
    }
  },
  props: ['tasksOll'],
  methods: {
    newItem() {
      if (!this.tasks.name) {
        return
      }
      for (let i = 0; i < this.tasksOll.length; i++) {
        if (this.tasksOll[i].name === this.tasks.name) {
          alert('This task already exists!')
            this.tasks.name = "";
            return;
        }
      }
      this.$emit('name-tasks', {
        'name': this.tasks.name
      });
      this.tasks.push ( {
        name: this.tasks.name,
        del: ''
      });
      this.tasks.name = "";
    },
  }
}
</script>

<style>
.submit-task {
  width: 32px;
  height: 32px;
  flex-shrink: 0;
  border: none;
  background-color: #ee9ca7;
  color: #fff;
  background-image: url("data:image/svg+xml,%3Csvg xmlns='http://www.w3.org/2000/svg' width='24' height='24' viewBox='0 0 24 24' fill='none' stroke='%23ffffff' stroke-width='2' stroke-linecap='round' stroke-linejoin='round' class='feather feather-plus'%3E%3Cline x1='12' y1='5' x2='12' y2='19'/%3E%3Cline x1='5' y1='12' x2='19' y2='12'/%3E%3C/svg%3E");
  background-size: 18px;
  background-position: center;
  background-repeat: no-repeat;
  border-radius: 50%;
  cursor: pointer;
}

.add-task {
  height: 40px;
  font-size: 14px;
  display: flex;
}
.task-input {
  border-right: none;
  width: 83%;
  padding: 0 4px;
  outline: none;
  border: none;
  border-bottom: 1px solid #fff;
  background-color: transparent;
  margin-right: 12px;
  color: #fff;
  box-shadow: none;
  border-radius: 0;
  height: 25px;
}


</style>