<script>
	export let movieDetails;
</script>

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
