<script>
  import Todo from "./Todo.svelte";

  let { list, deleteTask } = $props();
</script>



<div class="items">
  {#each list as item (item.id)}
    <Todo {...item} {deleteTask} />
  {/each}
</div>


<style>
  .items {
    display: flex;
    flex-direction: column;
    gap: 0.7rem;
    margin-top: 1rem;
  }
</style>
