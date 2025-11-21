<script>
  import CreateTask from "./lib/CreateTask.svelte";
  import List from "./lib/List.svelte";
  // import Todo from "./lib/Todo.svelte";
  let list = $state([
    // {id: 1, title: 'task1', status: false},
    // {id: 2, title: 'task1', status: false},
])

    const deleteTask = (id) => {
      list = list.filter(item => item.id !== id)
    }

    const submit = (e, title) => {
      e.preventDefault();
      if (title === '') return;
      title = '';
    }

    const addTask = (title) => {
      const task = {id: Date.now(), title: title, status: false}
      list = [task, ...list]
    }

</script>


<main>
  <CreateTask {submit} {addTask}/>
  <List {list} {deleteTask}/>
  <!-- <Todo/> -->
</main>


<style>
main {
  width: 700px;
}
</style>