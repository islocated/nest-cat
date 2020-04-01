<script>
	import {onMount} from 'svelte';

	import Cat from './Cat.svelte';

//	let facts = [];

	let images = [];

	onMount(async () => {
		/*
		const res = await fetch("https://cat-fact.herokuapp.com/facts");
		const json = await res.json();
		facts = json.all.filter(obj => obj.upvotes > 0);
		*/

		for(let i=0; i < 25; i++){
			const res = await fetch("https://aws.random.cat/meow");
			const json = await res.json();
			images = [...images, json.file];
		}

		/*
		for(let i=0; i < 12; i++){
			const res = await fetch("https://random.dog/woof.json");
			const json = await res.json();
			images = [...images, json.url];
		}
		*/
	});

</script>

<style>
	.cat-list {
		display: flex;
		flex-flow: row;
		flex-wrap: wrap;
		list-style: none;
	}

	.cat-list li {
		width: 100%;
		margin: 5px;
	}
</style>


<main>
	{#if images}
	<ul class="cat-list">
		{#each images as image}
			<li>
				<Cat {image} />
			</li>
		{/each}
	</ul>
	{/if}
</main>
