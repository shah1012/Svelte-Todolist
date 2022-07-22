<script>
  import { todos } from "../store";
</script>

<div class="todos">
  <ul class="todo-list">
    {#each $todos as todo}
      <li class:completed={todo.completed ? "completed" : ""}>
        <p>{todo.task}</p>
        <input
          type="checkbox"
          checked={todo.completed}
          on:click={(e) => {
            todo.completed = !todo.completed;
          }}
          class="check"
        />
        <button
          class="todo-del"
          on:click={() => ($todos = $todos.filter((t) => t.id !== todo.id))}
          >X</button
        >
      </li>
    {/each}
  </ul>
</div>

<style>
  .todos {
    margin: 30px;
    width: 500px;
    background-color: white;
    border-radius: 10px;
    height: 500px;
  }
  .todo-list {
    list-style: none;
    width: 100%;
    background-color: rgba(255, 255, 0, 0.646);
    height: 100%;
    border-radius: 10px;
    padding: 20px;
    overflow-y: auto;
  }

  .todo-list > li {
    border-radius: 15px;
    background-color: #66cccc;
    display: flex;
    align-items: center;
    height: 100%;
    max-height: 75px;
    padding: 20px;
    margin-bottom: 20px;
  }

  .todo-list > li > p {
    font-size: 1.5rem;
    color: white;
    flex: 1;
  }

  .todo-list > li > input {
    width: 30px;
    height: 30px;
    border-radius: 50%;
    cursor: pointer;
    margin-right: 10px;
  }

  .todo-del {
    font-size: 1.7em;
    padding: 2px 8px;
    border-radius: 10px;
    color: white;
    border: none;
    outline: none;
    cursor: pointer;
    background-color: red;
  }
  .completed {
    opacity: 0.5;
  }
</style>
