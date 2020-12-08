<script>
  let textInput = "";
  let todos = [];

  const addTodo = () => {
    if (textInput.length > 0) {
      todos = [...todos, textInput];
      textInput = "";
    }
  };
</script>

<style>
  #todo-wrapper {
    max-width: 500px;
    margin: 0px auto;
  }

  #todo-wrapper h1.title {
    text-align: center;
    color: white;
  }

  #todo-wrapper .horizontal-block {
    display: flex;
    width: 100%;
  }

  #todo-wrapper .horizontal-block input {
    width: 100%;
    margin-right: 10px;
  }
</style>

<div id="todo-wrapper">
  <h1 class="title">Todo List</h1>

  <div class="horizontal-block">
    <input
      bind:value={textInput}
      type="text"
      placeholder="Digite o valor da lista" />
    <button on:click={addTodo}>Adicionar</button>
  </div>

  {#if todos.length > 0}
    <ul>
      {#each todos as todo, i}
        <li>
          <p>{i} - {todo}</p>
        </li>
      {/each}
    </ul>
  {:else}
    <p>Sem itens ainda adicionados</p>
  {/if}
</div>
