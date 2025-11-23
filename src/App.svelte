<script>
  import CreateTask from "./lib/CreateTask.svelte";
  import List from "./lib/List.svelte";
  // import Todo from "./lib/Todo.svelte";

  // 1. створив тестовий масив для перевірки рендера
  let list = $state([   
    // {id: 1, title: 'task1', status: false},
    // {id: 2, title: 'task1', status: false},
])
    // 2. на видалення елемента списку
    const deleteTask = (id) => {
      list = list.filter(item => item.id !== id)
    }
    // 3. обробник submit зупинка перезавантаження , очистка title
    const submit = (e, title) => {
      e.preventDefault();
      if (title === '') return;
      title = '';
    }
    // 4. створення нового елемента на початок списку
    const addTask = (title) => {
      const task = {id: Date.now(), title: title, status: false}
      list = [task, ...list]
    }

    const saved = localStorage.getItem("tasks");
    if (saved) {
      list = JSON.parse(saved)
    }

    $effect(() => {
      localStorage.setItem("tasks", JSON.stringify(list));
    })

</script>


<main>
  <CreateTask {submit} {addTask}/>
  <List {list} {deleteTask}/>
  <!-- <Todo/> -->
</main>


<style>
main {
  width: 100%;
  max-width: 700px;
  margin: 0 auto;
}


</style>