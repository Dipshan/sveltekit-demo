<script context="module">
	export async function load({ fetch }) {
		const res = await fetch(
			'https://api.themoviedb.org/3/movie/popular?api_key=51482fa74ac76751b06652b48a0d5774&language=en-US&page=1'
		);
		const data = await res.json();

		if (res.ok) {
			return {
				props: { popular: data.results }
			};
		}
	}
</script>

<script>
	import { fly } from 'svelte/transition';
	import MovieCard from '../components/MovieCard.svelte';

	export let popular;

	let searchTerm = '';

	let loading = false;

	$: userSearch = popular.filter((m) => {
		return m.title.toLowerCase().includes(searchTerm);
	});
</script>

<div in:fly={{ y: 50, duration: 500 }} out:fly={{ duration: 500 }}>
	<div class="p-5 align-middle flex justify-evenly">
		<a href="/" class="text-2xl font-bold">Home</a>
		<h1 class="text-2xl font-bold">Popular Movies</h1>
		<form class="flex border align-middle justify-center border-black">
			<input
				class="outline-none p-2 text-white bg-neutral-800"
				type="text"
				bind:value={searchTerm}
				placeholder="Search movies here..."
			/>
			<!-- <button type="submit" class="p-2 border-black border-r-l flex align-middle">Search </button> -->
		</form>
	</div>
	<div class="p-10 grid grid-cols-5 gap-x-7 gap-y-10">
		{#if userSearch}
			{#each userSearch as movie}
				<MovieCard {movie} />
			{/each}
		{:else}
			<p>No movies found with name of {userSearch}</p>
		{/if}
	</div>
</div>
