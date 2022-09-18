<script> // 의존성이 제대로 resolve 되지 않음. -> pnp확인 필요
	import dayjs from 'dayjs'; 
	export let name;
	let todos = [];
	let value = '';

	const handleClick = () => {
		console.log({value})
		todos = [...todos, `${value}, ${dayjs.now()}`];
		value = ''
	}
</script>

<main>
	<h1>Hello {name}!</h1>
	<p>Visit the <a href="https://svelte.dev/tutorial">Svelte tutorial</a> to learn how to build Svelte apps.</p>
	<div>
		<h1>My Svelte Todo</h1>
		<ul>
			{#each todos as todo}
			<li>{todo}</li>
				
			{/each}
		</ul>
	</div>
	<div>
		<input bind:value={value} />
		<button on:click={handleClick}>Create Todo</button>
	</div>	
</main>

<style>
	main {
		text-align: center;
		padding: 1em;
		max-width: 240px;
		margin: 0 auto;
	}

	h1 {
		color: #ff3e00;
		text-transform: uppercase;
		font-size: 4em;
		font-weight: 100;
	}

	@media (min-width: 640px) {
		main {
			max-width: none;
		}
	}
</style>
