<script>
	import { todoStore } from './store.js';
	
	let text = '';
	const pushTodo = () => {
		if(text.length > 0) {
			todoStore.update(state => [text, ...state]);
			text = '';
		}
	}
	
</script>

<div>
	<input bind:value={text} placeholder="write a new todo">
	<button on:click={pushTodo}>Add</button>
</div>