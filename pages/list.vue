<template lang="pug">
  div.container
    h1 To-Vue List
    p
      nuxt-link(exact to="/") Home page
    h3 Add your tasks
    input(v-model="task",placeholder="Add a task")
    button(@click="addTask") Add

    ul
      li(v-for="t in tasks")
        b {{ t }}
</template>

<script>

export default {
  data () {
    return {
      task:'',
      tasks:[]
    }
  },
  methods: {
    addTask() {
      this.tasks.push(this.task)
      this.task = ''
    },
  }
}
</script>


<style>
  .container {
    font: "Quicksand";
    padding: 60px;
  }
</style>
