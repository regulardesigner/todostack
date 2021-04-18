<template>
  <div>
    <section class="todo">
      <ul class="task-list">
        <li class="task" v-for="todo in todos" :key="todo.id">
          {{ todo.title }}
        </li>
      </ul>
    </section>
    <section class="new-task">
      <button class="button button--add">Add a new task</button>
    </section>
    <section class="done">
      <ul class="task-list">
        <li class="task" v-for="doneTask in doneTasks" :key="doneTask.id">
          <small class="done-date">{{ getDoneDate(doneTask.doneDate) }}</small>
          <span class="task--done">{{ doneTask.title }}</span>
        </li>
      </ul>
    </section>
  </div>
</template>

<script>
export default {
  data() {
    return {
      tasks: [
        {
          id: 1,
          date: "1618737757816",
          title: "task une",
          done: true,
          doneDate: "1618737757816",
        },
        {
          id: 2,
          date: "1618737789315",
          title: "task deux",
          done: true,
          doneDate: "1618737789315",
        },
        {
          id: 3,
          date: "1618737873034",
          title: "task trois",
          done: true,
          doneDate: "1618737873034",
        },
        {
          id: 4,
          date: "1618737874035",
          title: "task quatre",
          done: true,
          doneDate: "1618737874035",
        },
        {
          id: 5,
          date: "1618737875036",
          title: "task cinq",
          done: false,
          doneDate: null,
        },
        {
          id: 6,
          date: "1618737876037",
          title: "task six",
          done: false,
          doneDate: null,
        },
        {
          id: 7,
          date: "1618737877038",
          title: "task sept",
          done: false,
          doneDate: null,
        },
      ],
      doneTasksCount: 0,
    };
  },

  computed: {
    todos() {
      return this.tasks.filter((task) => task.done === false);
    },

    doneTasks() {
      const dones = this.tasks.filter((task) => task.done === true);
      this.getDoneTaskCount(dones.length);
      return dones.reverse();
    },

    doneCounter() {
      alert(this.doneTasks.length());
      return this.doneTasks.length();
    },
  },

  methods: {
    getDoneTaskCount(val) {
      this.doneTasksCount = val;
    },

    getDoneDate(timestamp) {
      return new Intl.DateTimeFormat("fr-FR", {
        dateStyle: "long",
        timeStyle: "short",
      }).format(timestamp);
    },
  },
};
</script>

<style lang="scss">
.todo {
  .task {
    background-color: lightgoldenrodyellow;
  }
}

.done {
  .task {
    background-color: lightgrey;
  }
}

.task {
  font-size: 1rem;
  padding: 0.5rem;
  border-radius: 0.6rem;
  margin-bottom: 0.4rem;
  border: 1px solid transparent;

  &--done {
    display: block;
    color: #222;
    text-decoration-line: line-through;
    text-decoration-style: wavy;
    text-decoration-color: rgba(brown, 0.6);
  }

  &-list {
    margin: 1rem 0;
    padding: 0;
    list-style: none;
  }
}

.todo .task:nth-child(-n + 3) {
  border-color: rgba(orange, 0.4);
}

.done-date {
  text-transform: uppercase;
  font-family: "Courier New", Courier, monospace;
}
</style>
