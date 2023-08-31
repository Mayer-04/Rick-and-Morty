<script>
  export let character;
</script>

<div class="container-characters">
  <img src={character.image} alt={character.name} />
  <div>
    <h3>{character.name}</h3>
    <p>
      {character.status}
    </p>
    <p>{character.species}</p>
  </div>
</div>

<style>
  .container-characters {
    text-align: center;
    color: #fff;
  }

  h3 {
    font-weight: 600;
  }

  div {
    display: flex;
    flex-direction: column;
    gap: 10px;
  }
</style>
