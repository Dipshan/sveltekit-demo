<script>
	export let movie;
</script>

<div class="shadow-xl border border-black-500 rounded-xl hover:opacity-80">
	<a href={`/movie/${movie.id}`}>
		<img class="rounded-xl" src={'https://image.tmdb.org/t/p/w500' + movie.poster_path} alt={movie.title} />
		<div class="p-3">
			<h1 class="text-base font-bold">{movie.title}</h1>
			<p>Release Date: {movie.release_date}</p>
		</div>
    </a>
</div>
