<template>
  <div class="home">
    <list-tasks 
    v-if="$store.state.tasks.length" 
    />

    <no-tasks
    v-else />
   <DoneSorting v-if="$store.state.sorting"/>
  </div>

</template>

<script>
import ListTasks from '@/components/Todo/ListTasks.vue'
import NoTasks from '@/components/Todo/NoTasks.vue'
import DoneSorting from '@/components/Todo/ButtonDoneSorting.vue'

  export default {
    name: 'Home',
  
  components: {
    'list-tasks' : ListTasks,
    'no-tasks' : NoTasks,
    'DoneSorting': DoneSorting
  },
  
}
</script>

<style lang="sass">

</style>