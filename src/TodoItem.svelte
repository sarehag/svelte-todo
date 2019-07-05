<script>
  import { todoStore } from './store.js';
  export let index;
	
	let text;
	
	const unsubscribe = todoStore.subscribe(state => {
		text = state[index];
	});
	
	const remove = () => {
		todoStore.update(state => state.filter(todoItem => todoItem !== text))
	}
</script>

<style>
	div {
		display: flex;
		justify-content: space-between;
		padding: 8px 16px;
		border: 1px solid #ddd;
	}
</style>

<div>
	<span>{ text }</span>
	<button on:click={remove} >
		X
	</button>
</div>