<script lang="ts">
	export let value: string;
	import { createEventDispatcher } from 'svelte';

	const dispatch = createEventDispatcher();
	$: handleClick = () => dispatch('cmpBtnClick');
</script>

<div>Hello</div>
<button on:click={handleClick}>Button in Component</button>

<div>Value is here: {value}</div>
