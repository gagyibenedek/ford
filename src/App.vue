<template>
  <div id="app">
    <task v-for="(task, index) in tasks"
      v-bind:finished="task.finished"
      v-bind:name="task.name"
      @toggle="update(index, $event)">
    </task>
  </div>
</template>

<script>
import Vue from 'vue'
import Task from './components/Task'

export default {
  name: 'app',
  components: {
    Task
  },
  data () {
    return {
      tasks: [
        {
          finished: false,
          name: 'task1'
        },
        {
          finished: false,
          name: 'task2'
        },
        {
          finished: true,
          name: 'task3'
        }
      ]
    }
  },
  methods: {
    update (index, event) {
      Vue.set(this.tasks[index], 'finished', event)
    }
  }
}
</script>

<style>
#app {
  font-family: 'Avenir', Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
