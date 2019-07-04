<script>
	import { todoStore } from './store.js';
	import TodoItem from './TodoItem.svelte';

	let noOfTodos = 0;

	const unsubscribe = todoStore.subscribe(state => {
		noOfTodos = state.length;
	});
</script>

{#if noOfTodos === 0}
	<div>
		Nothing todo!
	</div>
{/if}

{#each [...Array(noOfTodos).keys()] as index}
	<TodoItem index={index} />
{/each}