<script>
  // Se definen los valores iniciales de las variables que se utilizaran
  let newItem = '';
  let todos = [];

  // Funcion para agregar un objeto a la lista
  function addTodo() {
    if (newItem.trim() !== '') {
      todos = [...todos, { id: Date.now(), text: newItem, completed: false }];
      newItem = '';
    }
  }
  
  // Funcion para cambiar un objeto de la lista a "completado"
  function toggleCompleted(id) {
    todos = todos.map(todo =>
    todo.id === id ? { ...todo, completed: !todo.completed } : todo
  );
}

// Funcion para remover un objeto de la lista
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
  <!-- Input que permite agregar objetos a la lista  -->
  <input type="text" bind:value={newItem} placeholder="Enter a new task" />
  <button on:click={addTodo}>Add</button>
  
  <ul>
    <!-- Visualizacion del listado de quehaceres -->
    {#each todos as todo (todo.id)}
      <li class='todo-item' class:completed={todo.completed}>
        <input type="checkbox" checked={todo.completed} on:change={() => toggleCompleted(todo.id)} />
        <span>{todo.text}</span>
        <span class="delete-button" on:click={() => removeTodo(todo.id)}>❌</span>
      </li>
    {/each}
  </ul>
</div>
