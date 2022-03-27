<script context="module">
	export async function load({ fetch, params }) {
		// console.log(params);
		const id = params.id;
		const res = await fetch(
			`https://api.themoviedb.org/3/movie/${id}?api_key=51482fa74ac76751b06652b48a0d5774&language=en-US`
		);
		const movieDetails = await res.json();
		// console.log(movieDetails);

		if (res.ok) {
			return {
				props: { movieDetails }
			};
		}
	}
</script>

<script>
	export let movieDetails;
</script>

<div class="p-10">
	<div class="flex align-middle justify-around mb-10">
		<h1 class="text-3xl">Movie Detail</h1>
		<button class="border border-black px-2 rounded hover:text-white hover:bg-slate-900"
			><a href="/movies">Go back</a></button
		>
	</div>

	<div class="flex shadow-xl justify-center align-middle rounded-xl border border-black-500">
		<img
			class="rounded-xl w-60 h-auto"
			src={'https://image.tmdb.org/t/p/w500' + movieDetails.poster_path}
			alt={movieDetails.title}
		/>
		<div class="p-5">
			<h1 class="text-3xl mb-1 font-bold">{movieDetails.title}</h1>
			<p class="text-lg mb-3">{movieDetails.tagline}</p>
			<p class="mb-3"><span class="font-semibold">Release Date: </span> {movieDetails.release_date}</p>
			<p class="mb-3"><span class="font-semibold">Status: </span>{movieDetails.status}</p>
			<div class="flex gap-x-5 mb-3">
				<p><span class="font-semibold">Runtime: </span>{movieDetails.runtime} min</p>
				<p><span class="font-semibold">Ratings: </span>{movieDetails.vote_average}</p>
			</div>
			<p class="text-lg font-semibold mb-1">Synopsis:</p>
			<p class="font-mono font-semibold text-justify">{movieDetails.overview}</p>
		</div>
	</div>
</div>
