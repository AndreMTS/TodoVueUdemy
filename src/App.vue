<template>
  <div id="app">
    <h1>Tarefas</h1>
    <TaskGrid :tasks="tasks" />
  </div>
</template>

<script>
import TaskGrid from './components/TaskGrid.vue'

export default {
  components: {TaskGrid},
  data() {
    return {
      tasks: [
        {name: 'Lavar louça', pending: false},
        {name: 'Comprar comida', pending: true},
      ]
    }
  },
};
</script>

<style scoped>
header {
  line-height: 1.5;
}

.logo {
  display: block;
  margin: 0 auto 2rem;
}

@media (min-width: 1024px) {
  header {
    display: flex;
    place-items: center;
    padding-right: calc(var(--section-gap) / 2);
  }

  .logo {
    margin: 0 2rem 0 0;
  }

  header .wrapper {
    display: flex;
    place-items: flex-start;
    flex-wrap: wrap;
  }
}
</style>
