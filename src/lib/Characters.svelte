<script>
  import { fade } from "svelte/transition";
  export let character;

  const { image, name, status, species } = character;

  const characterStatus = {
    alive: "Alive",
    dead: "Dead",
    unknown: "unknown",
  };

  const { alive, dead, unknown } = characterStatus;
</script>

<div transition:fade class="container-characters">
  <img src={image} alt={name} />
  <div class="information">
    <h3>{name}</h3>
    <p
      class="status"
      class:alive={status === alive}
      class:dead={status === dead}
      class:unknown={status === unknown}
    >
      {status}
    </p>
    <p>{species}</p>
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
    height: auto;
    object-fit: cover;
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
