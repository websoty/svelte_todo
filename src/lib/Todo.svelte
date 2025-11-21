<script>
  let { id, title, status, deleteTask } = $props();
</script>

<div class="todo {status ? 'checked' : ''}">
  <input type="checkbox" bind:checked={status} />
  <h2>{title}</h2>
  <button onclick={() => deleteTask(id)}>delete </button>
</div>

<style>
  .todo {
    border: 1px solid #ccc;
    padding: 1rem;
    display: flex;
    align-items: center;
    justify-content: space-between;
    background: #708688;
    border-radius: 10px;
    transition: .3s ease-out;
  }

  .checked {
    text-decoration: line-through;
    opacity: 0.8;
    background: #0d3a44;
  }

  .todo h2 {
    font-size: 1.5rem;
    margin: 0;
    flex: 1; 
  }

   input[type="checkbox"] {
    width: 22px;
    height: 22px;
    cursor: pointer;
  }

    button {
    padding: 0.3rem 0.7rem;
    font-size: 0.9rem;
    border: none;
    border-radius: 6px;
    background: #ff4d4f;
    color: #fff;
    cursor: pointer;
    transition: background 0.2s;
  }

  button:hover {
    background: #d9363e;
  }
  
</style>
