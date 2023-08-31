<script>
  export let character;
</script>

<div>
  <img src={character.image} alt={character.name} />
  <h3>{character.name}</h3>
  <p>{character.status}</p>
  <p>{character.species}</p>
</div>
