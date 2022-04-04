<script context="module">
  export async function load({ fetch }){
    const resp = await fetch(
      `https://api.themoviedb.org/3/movie/popular?api_key=${import.meta.env.VITE_API}&language=ja-JP&page=1`
    );
    const data = await resp.json();
    console.log(data)
    if(resp.ok){
      return{
        props:{ popular:data.results }
      };
    }
  }
</script>

<script>
  import SearchMovies from "../components/SearchMovies.svelte"
  import PopularMovies from "../components/PopularMovies.svelte";
  export let popular;
</script>

<section>
  <SearchMovies />
  <PopularMovies {popular} />
</section>