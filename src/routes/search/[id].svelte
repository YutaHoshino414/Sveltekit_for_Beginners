<script context="module">
  export async function load({ fetch, params }){
    const resp = await fetch(
      `https://api.themoviedb.org/3/search/movie?api_key=${import.meta.env.VITE_API}&language=ja-JP&query=${params.id}&page=1&include_adult=false`
    );
    const data = await resp.json();
    console.log(data)
    if(resp.ok){
      return{
        props:{ searchedMovie:data.results }
      };
    }
  }
</script>

<script>
  import MovieCard from '../../components/MovieCard.svelte'
  export let searchedMovie;
</script>

<div class="outer">
  <div class="searched-movies">
    {#each searchedMovie as movie}
      <MovieCard {movie} />
    {/each}
  </div>
</div>

<style>
  .outer {
    margin-top: 30px;
  }
  .searched-movies {
    display: grid;
    grid-template-columns: repeat(auto-fit, minmax(250px, 1fr));
    grid-column-gap: 1rem;
    grid-row-gap: 2rem;
    height: 20vh;
  }
</style>