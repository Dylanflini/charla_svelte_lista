<script>
  export let searchedCountry = "",
    theme;
</script>

<style>
  label,
  input {
    background: var(--second-background);
  }

  label {
    display: flex;
    width: 50%;
    min-width: 250px;
    height: 2rem;
    padding: 0.5rem;
    border: 0;
    border-radius: 4px;
    box-shadow: var(--boxshadow);
  }

  label:focus-within {
    outline: var(--outline);
  }

  input {
    color: var(--color);
    border-radius: 4px;
    padding: 0.4rem;
    font-size: 1rem;
    padding-left: 0.5rem;
    width: calc(100% - (20px + 0.8rem));
    border: 0;
    outline: none;
  }

  img {
    width: 20px;
    fill: red;
  }
</style>

<label for="country-input">
  {#if theme.name === 'dark'}
    <img src="loupe-dark.svg" alt="" />
  {:else}<img src="loupe-light.svg" alt="" />{/if}
  <input
    name="country-input"
    id="country-input"
    bind:value={searchedCountry}
    placeholder="Search for a country..." />
</label>
