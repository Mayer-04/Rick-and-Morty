<script>
  export let character;

  const characterStatus = {
    alive: "Alive",
    dead: "Dead",
    unknown: "unknown",
  };

  const { alive, dead, unknown } = characterStatus;
</script>

<div class="container-characters">
  <img src={character.image} alt={character.name} />
  <div class="information">
    <h3>{character.name}</h3>
    <p
      class="status"
      class:alive={character.status === alive}
      class:dead={character.status === dead}
      class:unknown={character.status === unknown}
    >
      {character.status}
    </p>
    <p>{character.species}</p>
  </div>
</div>

<style>
  .container-characters {
    background-color: #3c3e44;
    text-align: center;
    color: #fff;
    border-radius: 10px;
  }

  img {
    width: 100%;
    border-radius: 10px 10px 0 0;
  }

  h3 {
    font-weight: 600;
  }

  .information {
    display: flex;
    flex-direction: column;
    gap: 10px;
    padding: 15px 0;
  }
  .status {
    font-weight: 600;
    font-style: italic;
  }

  .alive {
    color: #18be18;
  }

  .dead {
    color: #ff0000;
  }

  .unknown {
    color: #ffff00de;
  }
</style>
