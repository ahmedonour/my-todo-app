<!-- TodoList.svelte -->
<script>
	export let todos = [];
	export let deleteTodo;
</script>

{#each todos as todo}
	<div class="todo">
		<div class="todo-text">{todo.text}</div>
		<button class="todo-delete" on:click={() => deleteTodo(todo.id)}> Delete </button>
	</div>
{/each}

<style>
	.todo {
		display: flex;
		align-items: center;
		justify-content: center;
		color: white;
		width: 100vw;
		padding-inline: 3rem;
	}

	.todo-text {
		/* flex-grow: 1; */
		margin: 1rem;
		width: 50vw;
	}

	.todo-delete {
		margin: 1rem;
		height: 3rem;
		background-color: rgb(255, 54, 54);
		border: none;
		outline: none;
		width: 100px;
		color: white;
		font-family: 'Montserrat', sans-serif;
		font-weight: 800;
		border-radius: 20px;
	}
	@media screen and (max-width: 414px){
		.todo-text{
			width: 85vw;
		}
		.todo-delete{
			width: 40vw;
		}
	}
</style>
