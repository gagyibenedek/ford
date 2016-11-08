<template>
  <div class="task">
    <input type="checkbox" :checked="finished" v-on:click="toggle" />
    <label class="task-name" :class="{finished:finished}">{{name}}</label>
  </div>
</template>

<script>
export default {
  name: 'hello',
  props: {
    'finished': {
      type: Boolean,
      required: true
    },
    'name': {
      type: String,
      required: true
    }
  },
  methods: {
    toggle () {
      this.$emit('toggle', !this.finished)
    }
  }
}
</script>

<style scoped>
.task-name {
  vertical-align: top;
}

.task-name.finished {
  text-decoration: line-through;
}

</style>
