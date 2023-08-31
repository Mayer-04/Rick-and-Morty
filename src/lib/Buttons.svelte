<script>
  export let page;
  export let fetchCharacters;

  const nextPage = () => {
    fetchCharacters(page + 1);
  };
  const previousPage = () => {
    fetchCharacters(page - 1);
  };
</script>

<div>
  <button on:click={previousPage}>Anterior</button>
  <button on:click={nextPage}>Siguiente</button>
</div>
