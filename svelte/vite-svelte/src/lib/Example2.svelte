<script>
  let newItem = '';
  let todos = [];

  function addTodo() {
    if (newItem.trim() !== '') {
      todos = [...todos, { id: Date.now(), text: newItem, completed: false }];
      newItem = '';
    }
  }

  function toggleCompleted(id) {
    todos = todos.map(todo =>
      todo.id === id ? { ...todo, completed: !todo.completed } : todo
    );
  }

  function removeTodo(id) {
    todos = todos.filter(todo => todo.id !== id);
  }
</script>

<style>
  .todo-item {
    margin-bottom: 10px;
  }

  .completed {
    text-decoration: line-through;
  }

  .delete-button {
    margin-left: 10px;
    cursor: pointer;
  }
</style>

<div>
  <h1>Ejemplo #2</h1>
  <input type="text" bind:value={newItem} placeholder="Enter a new task" />
  <button on:click={addTodo}>Add</button>

  <ul>
    {#each todos as todo (todo.id)}
      <li class='todo-item' class:completed={todo.completed}>
        <input type="checkbox" checked={todo.completed} on:change={() => toggleCompleted(todo.id)} />
        <span>{todo.text}</span>
        <span class="delete-button" on:click={() => removeTodo(todo.id)}>❌</span>
      </li>
    {/each}
  </ul>
</div>
