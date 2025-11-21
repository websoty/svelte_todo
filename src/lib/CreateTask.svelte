<script>
  let { submit, addTask } = $props();
  let title = $state("");
</script>

<!-- 1 розмітка форми
     2 привязав поле інпута до стейта title
     3 передав пропси на форму і кнопку 
      -->
<form onsubmit={(e) => submit(e, title)}>
  <input 
  type="text" 
  bind:value={title} />

  <button
  disabled={title === ''}
  onclick={() => {addTask(title); title = '';}}

  >Add task</button>
  
</form>

<style>
  form {
    display: flex;
    gap: 0.4rem;
    align-items: center;
    margin-bottom: 0.7rem;
  }

  input {
    flex: 1;
    padding: 0.55rem 0.7rem;
    font-size: 1.1rem;
    border-radius: 6px;
    border: 1px solid #ccc;
    outline: none;
    transition: .3s ease-out;
  }

  input:focus {
    border-color: #007bff;
  }

  button {
    font-size: 1rem;
    border: none;
    border-radius: 6px;
    background-color: #007bff;
    color: white;
    cursor: pointer;
    transition: .3s ease-out;
  }

  button:hover {
    background-color: #005fcc;
  }

  button:disabled {
    background-color: #aaa;
    cursor: not-allowed;
  }

  @media (max-width: 480px) {
  form {
    flex-direction: column;
    align-items: stretch;
  }

  input {
    width: 100%;
  }

  button {
    margin-top: 10px;
    width: 50%;
    align-self: center;
  }
}

</style>