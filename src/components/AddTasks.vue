<template>
    <div>
      <div v-for="task in tasks" :key="task.id">
        <OnlyTask
          @toggle-reminder="$emit('toggle-reminder', task.id)"
          @delete-task="$emit('delete-task', task.id)"
          :task="task"
        />
      </div>
    </div>
  </template>

<script>
import OnlyTask from "./OnlyTask.vue"

export default {
    name : "AddTasks",
    props :{
        tasks: {
            type: Array,
            default: () =>[]
        }
    },
    components: {
        OnlyTask
    },
    emits: ['delete-task', 'toggle-reminder']
}
</script>