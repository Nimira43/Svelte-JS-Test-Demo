<script>
	let note = ''
	let note_id = 0
	let notes = [
		{
			id: 0,
			content: 'Learn more Svelte JS',
			editing: false
		}
	]
	function saveNote() {

	}
</script>

<main>
	<div class="body">
		<form on:submit|preventDefault={saveNote}>
			<h2>Add Note...</h2>
			<textarea
				bind:value={note}
				placeholder="Type note"
			></textarea>
			<input type="submit" value="Save" />
		</form>
		<hr>
		<h2>Latest Notes</h2>
		{#if notes.length > 0}
			{#each notes as note}
				<div> 
					<p class="notes">{note.content}</p>
					<hr>
					<button>Delete</button>
					<button>Edit</button>
				</div>
			{/each}
		{:else}
			<p>There is not any notes</p>
		{/if}
	</div>
</main>

<style>
	main {
		text-align: center;
		padding: 1em;
		width: 100%;
		height: 100vh;
		display: flex;
		justify-content: center;
		align-items: center;
		overflow: hidden;
	}

	h2 {
		color: gold;
	}

	main .body {
		width: 80%;
		height: 80%;;
		background-color: black;
		padding: 30px;
	}

	textarea {
		width: 80%;
		height: 25vh;
		background-color: gold;
		outline: none;
		border: none;
		color: black;
	}

	input {
		display: block;
		margin: 20px auto;
	}

	button {
		margin: 20px 40px;
	}

	input,
	button {
		
		color: gold;
		background-color: red;
		padding: 10px 30px;
		outline: none;
		border: none;
		font-size: 22px;
		font-weight: bold;
		cursor: pointer;
		transition: background-color 1s ease-in;
	}

	input:hover,
	button:hover {
		background-color: blue;
	}

	hr {
		color: blue;
	}

	main .notes {
		color: red;
		font-size: 20px;
	}

	
</style>