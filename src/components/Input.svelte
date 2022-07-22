<script>
  import { todos } from "../store";

  let value = "";

  const onAdd = () => {
    $todos = [
      ...$todos,
      {
        // use less crap id for todo
        id: $todos.length + 1,
        task: value,
        completed: false,
      },
    ];
    let x = $todos.map((td) => td.task);
    console.log(x);
    localStorage.setItem("todos", x);
    value = "";
  };
</script>

<form class="inputWrapper" on:submit|preventDefault={onAdd}>
  <input type="text" bind:value class="todoInput" />
  <button class="todoSubmit">Add</button>
</form>

<style>
  .inputWrapper {
    width: 100%;
    display: flex;
    flex-direction: row;
    justify-content: center;
    margin-top: 5%;
  }

  .todoInput {
    width: 500px;
    border: none;
    outline: none;
    font-size: 1.5rem;
    border-radius: 20px;
    margin-right: 20px;
    padding: 10px;
  }

  .todoSubmit {
    border: none;
    outline: none;
    cursor: pointer;
    font-size: 1.5rem;
    padding: 20px;
    background-color: rgba(255, 255, 0, 0.646);
    color: white;
    border-radius: 20px;
  }
</style>
