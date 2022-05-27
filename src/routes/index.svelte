<script lang="ts">
	import Component from '$lib/components/Component.svelte';

	let c2: any;
	const renderButton = () => {
		const cmp = document.querySelector('#cmp');
		c2 = new Component({
			target: cmp as Element,
		});
		c2.$on('cmpBtnClick', () => {
			counter++;
		});
	};

	$: counter = 0;
	$: {
		c2?.$set({ value: counter });
	}
</script>

<button on:click={renderButton}>Click</button>

<div id="cmp">
	<div id="hello2">Hello2</div>
</div>
