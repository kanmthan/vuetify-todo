<template>
      <v-list
      class="pt-0"
      flat
    >    
   <draggable 
   v-model="tasks"
   handle=".handle">
   <div v-if="tasks.length" >
    <task 
     v-for="task in tasks" 
     :key=task.id
     :task="task"
     />
   </div>
   <div class="no-data text-h5 primary--text" v-else>
        No Data Matches
    </div>
   </draggable>
    </v-list>
</template>

<script>
import draggable from "vuedraggable";
import Task from '@/components/Todo/Task.vue'

export default {
computed:{
    tasks: {
        get() {
            return this.$store.getters.tasksFiltered
        },
        set(value){
            this.$store.dispatch('setTasks', value)
        }
    }
},
components: {
    task : Task,
    draggable: draggable
}
}
</script>

<style lang="sass">
.no-data
  position: absolute
  left: 50%
  top: 50%
  transform: translate(-50%, -50%)
  
</style>