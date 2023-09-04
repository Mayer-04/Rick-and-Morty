<script>
  export let buttonType = "primary";
</script>

<button class={buttonType} on:click>
  <slot />
</button>

<style>
  .primary {
    cursor: pointer;
    border: 0;
    border-radius: 6px;
    padding: 8px 12px;
    font-weight: 500;
    box-shadow: 1px 2px 3px rgba(0, 0, 0, 0.2);
  }
  .secondary {
    background-color: #ff9800;
    color: #fff;
    cursor: pointer;
    border: 0;
    border-radius: 6px;
    padding: 8px 12px;
    font-weight: 500;
    box-shadow: 1px 2px 3px rgba(0, 0, 0, 0.2);
  }
</style>
