<script>
  import Todo from "./Todo.svelte";

  let { list, deleteTask } = $props();
</script>


<!-- 1 передав масив через пропс,
     2 цикл по масиву + ключ
     3 для кожного елемента передав поля id/title/status в компонент Todo
     4 передав функцію пропсом на видалення 1 елемента списку
 -->
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
