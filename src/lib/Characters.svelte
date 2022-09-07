<script>
    export let character;
</script>

<div class="card m-2" style="width: 18rem;">
    <img src={character.image} class="card-img-top" alt={character.name}>
    <div class="card-body">
      <h5 class="card-title">{character.name}</h5>
      <p class="card-text">{character.species}</p>
      <a href="/" class="btn btn-primary">Go somewhere</a>
    </div>
</div>