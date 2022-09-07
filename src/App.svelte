<script>
  import Character from './lib/Characters.svelte';

  let characters = [];
  let page = 1;
  async function loadCharacters(){
    const response = await fetch('https://rickandmortyapi.com/api/character?page='+page);
    const data = await response.json();
    characters = data.results;
    console.log(characters);
  }
  loadCharacters();

  function nextPage(){
    page++;
    loadCharacters();
  }
  function prevPage(){
    page--;
    loadCharacters();
  }
</script>

<main>
  <div class=" container button">
    <button on:click={nextPage}  class="btn-primary">NEXT</button>
    <button on:click={prevPage} disabled={page === 1} class="btn-primary">PREV</button>
  </div>
  <div class="container d-grid" style="flex-wrap: wrap;">
    {#each characters as chars}
      <Character character={chars} />
    {/each}
  </div>
</main>

