<script>
  export let page;
  export let fetchCharacters;

  const nextPage = () => {
    fetchCharacters(page + 1);
  };
  const previousPage = () => {
    if (page > 1) {
      fetchCharacters(page - 1);
    }
  };
</script>

<div class="container-buttons">
  <button class="previous" on:click={previousPage}>Anterior</button>
  <button class="next" on:click={nextPage}>Siguiente</button>
</div>

<style>
  .container-buttons {
    display: flex;
    justify-content: space-evenly;
    margin-top: 30px;
  }

  .previous {
    background-color: rgb(255, 152, 0);
    color: #fff;
    padding: 10px;
    cursor: pointer;
  }
  .next {
    background-color: #fff;
    border: none;
    padding: 10px;
    cursor: pointer;
  }
</style>
