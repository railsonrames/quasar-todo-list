<template>
  <q-page class="bg-grey column">
    <q-list class="bg-white" separator bordered>
      <q-item
        v-for="task in tasks"
        :key="task.title"
        @click="task.done = !task.done"
        clickable
        :class="{ 'done' : task.done}"
        v-ripple
      >
        <q-item-section avatar>
          <q-checkbox class="no-pointer-events" v-model="task.done" color="primary" />
        </q-item-section>
        <q-item-section>
          <q-item-label>{{ task.title }}</q-item-label>
        </q-item-section>
      </q-item>
    </q-list>
  </q-page>
</template>

<script>
export default {
  data() {
    return {
      tasks: [
        {
          title: "Estudar Vue.js",
          done: true
        },
        {
          title: "Estudar Knockout.js",
          done: false
        },
        {
          title: "Dominar C#",
          done: true
        },
        {
          title: "Iniciar meu pet project",
          done: false
        }
      ]
    };
  }
};
</script>

<style lang="scss">
.done {
  .q-item__label {
    text-decoration: line-through;
    color: #bbb;
  }
}
</style>
