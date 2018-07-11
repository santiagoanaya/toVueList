<template lang="pug">
  div.container
    h1 To-Vue List
    p
      nuxt-link(exact to="/") Home page
    h3 Add your tasks
    input(v-model="task", placeholder="Add a task")
    button(@click="addTask") Add

    ul Tasks
      li(v-for="t in tasks")
        b {{ t }}
        button(@click="finishTask(t)") Finished

    ul Completed
      li(v-for="c in completed")
        b {{ c }}
</template>

<script>
export default {
  data () {
    return {
      task:'',
      tasks:[],
      completed:[]
    }
  },
  methods: {
    addTask() {
      this.tasks.push(this.task)
      this.task = ''
    },
    finishTask(completedTask) {
      this.completed.push(completedTask)
      this.tasks.splice( this.tasks.indexOf(completedTask), 1 )
    }
  }
}
</script>


<style>
  .container {
    font: "Quicksand";
    padding: 60px;
  }
</style>
