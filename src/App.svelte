<script>
	import axios from 'axios';
	import { onMount } from 'svelte';
	import Home from './components/Home.svelte';
	export let name;
	let data;
	onMount(()=> getData());
	const getData = () => {
		axios.get('https://port-folio-builder.herokuapp.com/profile/5e8f07fbe24c958234f076f5').then(response => data = response.data);
	}


</script>

<main>
	{#if data !== undefined}
	<Home data={data}/>
	{:else}
	<p>loading</p>
	{/if}
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