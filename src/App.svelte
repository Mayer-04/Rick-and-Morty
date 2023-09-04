<script>
  import "./app.css";
  import Button from "./lib/Button.svelte";
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
      return (page = newPage);
    } catch (error) {
      throw new Error(`Error obtaining characters: ${error}`);
    }
  };
  fetchCharacters(page);

  const handleNextPage = () => {
    if (page < 42) {
      fetchCharacters(page + 1);
    }
  };

  const handlePreviousPage = () => {
    if (page > 1) {
      fetchCharacters(page - 1);
    }
  };
</script>

<main>
  <header>
    <h1>Rick and Morty API</h1>
    <div class="container-buttons">
      <Button on:click={handlePreviousPage} buttonType="secondary">
        Anterior
      </Button>
      <Button on:click={handleNextPage}>Siguiente</Button>
    </div>
  </header>
  <section>
    {#each characters as character (character.id)}
      <Characters {character} />
    {/each}
  </section>
  <footer class="footer">
    <p class="footer-text">Creado por Mayer Chaves</p>
  </footer>
</main>
