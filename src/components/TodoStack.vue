<template>
  <div>
    <section class="todo">
      <ul class="task-list">
        <li class="task">task four</li>
        <li class="task">task five</li>
        <li class="task">task six</li>
        <li class="task">task seven</li>
      </ul>
    </section>
    <section class="new-task">
      <button class="button button--add">Add a new task</button>
    </section>
    <section class="done">
      <ul class="task-list">
        <li class="task task--done">task three</li>
        <li class="task task--done">task two</li>
        <li class="task task--done">task one</li>
      </ul>
    </section>
  </div>
</template>

<style lang="scss">
.task {
  font-size: 1rem;
  padding: 0.5rem;
  border-radius: 0.4rem;
  margin-bottom: 0.4rem;
  background-color: lightgoldenrodyellow;
  border: 1px solid transparent;

  &--done {
    color: #222;
    background-color: whitesmoke;
    text-decoration-line: line-through;
    text-decoration-style: wavy;
    text-decoration-color: rgba(orange, 0.8);
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
</style>
