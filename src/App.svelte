<script>
  import Buttons from "./lib/Buttons.svelte";
  import Characters from "./lib/Characters.svelte";

  let characters = [];
  let page = 1;

  /**
   * @param {number} newPage
   */

  const fetchCharacters = async (newPage) => {
    try {
      const URL = `https://rickandmortyapi.com/api/character?page=${newPage}`;
      const response = await fetch(URL);
      const data = await response.json();
      characters = data.results;
      page = newPage;
    } catch (error) {
      throw new Error(`Error obtaining characters: ${error}`);
    }
  };
  fetchCharacters(page);
</script>

<main>
  <h1>Rick and Morty API</h1>
  <section>
    <!-- Componente para cambiar de página -->
    <Buttons {page} {fetchCharacters} />
    {#each characters as character}
      <Characters {character} />
    {/each}
  </section>
  <footer>
    <p>Creado por Mayer Chaves</p>
  </footer>
</main>
