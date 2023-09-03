<script>
  export let content;
</script>

<button class="change-pages" on:click>{content}</button>

<style>
  .change-pages {
    background-color: #fff;
    font-weight: 500;
    color: #000;
    padding: 10px;
    cursor: pointer;
    border-radius: 10px;
    border: none;
  }
</style>
