<script>
  export let movie;
</script>

<div class="movie-card">
  <img src={'https://image.tmdb.org/t/p/w500' + movie.poster_path } alt={movie.title} />
  <div class="discription">
    <h3>{movie.title}</h3>
    <p>{movie.release_date}</p>
  </div>
</div>

<style>
  img {
    width: 100%;
    height: 350px;
    
    object-fit: cover;
    border-radius: 1rem;
    margin-bottom: 1rem;
  }

  h3 {
    font-size: 0.9rem;
  }

  .description {
    height: 5vh;
  }

  p{
    font-size: 0.7rem;
  }

  .movie-card {
    display: flex;
    flex-direction: column;
    justify-content: space-around;
    padding: 1rem;
  }
</style>