<!-- App.svelte -->
<script>
	import TodoList from '../components/TodoList.svelte';
	import TodoForm from '../components/TodoForm.svelte';

	let todos = [
		{ id: 1, text: 'Wellcome' },
		{ id: 2, text: 'To' },
		{ id: 3, text: 'my Todo' },
		{ id: 4, text: 'app' }
	];
	let text;

	function addTodo(text) {
		todos = [...todos, { id: Date.now(), text }];
	}

	function deleteTodo(id) {
		todos = todos.filter((todo) => todo.id !== id);
	}
</script>

<div class="todo-container">
	<TodoForm {addTodo} />
	<div class="todo-list">
		<TodoList {todos} {deleteTodo} />
	</div>
</div>

<style>
	.todo-list {
		margin-top: 5rem;
	}
	.todo-container {
		max-width: 500px;
	}
</style>
