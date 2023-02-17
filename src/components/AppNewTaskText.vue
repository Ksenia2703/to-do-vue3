<template>
  <ul class="task-list">
    <li class="task-list-item"
        v-for="task in tasks"
        :key="task.name">
      <label class="task-list-item-label">
        <input type="checkbox">
        <span>{{task.name}}</span>
      </label>
      <span class="delete-btn"
            title="Delete Task"
            @click="delItem(task)">
        {{task.del}}
      </span>
    </li>
  </ul>
</template>

<script>
export default {
  data() {
    return{
      task: {}
    }
  },
  name: "AppNewTaskText",
  props: ['tasks'],
  methods: {
    delItem(task) {
      this.$emit('del-tasks', this.tasks.indexOf(task));
    }
  }
}
</script>

<style>
.task-list-item {
  background-color: #191933;
  border-radius: 4px;
  margin-bottom: 12px;
  display: flex;
  align-items: center;
  padding: 8px;
}

.delete-btn {
  margin-left: auto;
  display: block;
  width: 16px;
  height: 16px;
  background-repeat: no-repeat;
  background-image: url("data:image/svg+xml,%3Csvg xmlns='http://www.w3.org/2000/svg' width='24' height='24' viewBox='0 0 24 24' fill='none' stroke='%23ff3d46' stroke-width='2' stroke-linecap='round' stroke-linejoin='round' class='feather feather-trash-2'%3E%3Cpolyline points='3 6 5 6 21 6'/%3E%3Cpath d='M19 6v14a2 2 0 0 1-2 2H7a2 2 0 0 1-2-2V6m3 0V4a2 2 0 0 1 2-2h4a2 2 0 0 1 2 2v2'/%3E%3Cline x1='10' y1='11' x2='10' y2='17'/%3E%3Cline x1='14' y1='11' x2='14' y2='17'/%3E%3C/svg%3E");
  background-size: 16px;
  background-position: center;
  cursor: pointer;
}

input:checked {
  background-size: 10px;
  border: 1px solid rgb(0 43 99 / 8%);
}

input:checked + span {
  color: rgba(255, 255, 255, 0.5);
  text-decoration: line-through rgba(255, 255, 255, 0.8); }
</style>