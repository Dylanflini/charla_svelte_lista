<script>
  export let borders = [];
  $: {
    console.log(borders);
  }
</script>

<style>
  div {
    display: flex;
    align-items: center;
    opacity: var(--text-opacity);
    color: var(--color);
  }

  span {
    margin: 1rem;
  }
</style>

<div>
  <strong>BorderCountries: </strong>
  {#each borders.flat() as name}<span>{name}</span>{/each}
</div>
