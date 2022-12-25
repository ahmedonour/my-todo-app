<!-- TodoForm.svelte -->
<script>
	export let addTodo;
	let todoText = '';

	function handleSubmit(event) {
		event.preventDefault();
		addTodo(todoText);
		todoText = '';
	}
</script>

<form class="bg" on:submit|preventDefault={handleSubmit}>
	<input type="text" bind:value={todoText} placeholder="Add a todo..." />
	<button type="submit">Add</button>
</form>

<style>
	form {
		display: flex;
		background-color: rgb(149, 225, 255);
		width: 100vw;
		height: 40vh;
		padding: 3rem;
		justify-content: center;
		align-items: center;
		border-radius: 0px 0px 5rem 5rem;
	}
	.bg {
		width: 100vw;
		height: 40vh;
		background-image: radial-gradient(rgb(82, 0, 255, 0.4) 10%, transparent 10%);
		background-position: 0% 0%;
		background-size: 5vmin 5vmin;

		transition: all 400ms ease;
	}
	input[type='text'] {
		width: 50vw;
		height: 4rem;
		flex-grow: 1;
		font-family: 'Montserrat', sans-serif;
		font-weight: 900;
		padding: 1rem;
		border: none;
		outline: none;
		border-radius: 20px 0px 0px 20px;
	}
	button {
		height: 4rem;

		background-color: green;
		border: none;
		outline: none;
		width: 100px;
		color: white;
		font-family: 'Montserrat', sans-serif;
		font-weight: 800;
		border-radius: 0 20px 20px 0;
	}
	@media screen and (max-width: 414px){
		input[type='text']{
			width: 85vw;
		}
	}
</style>
