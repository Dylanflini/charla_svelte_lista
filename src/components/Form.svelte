<script>
  import Container from "./Container.svelte";
  import CountrySearch from "./CountrySearch.svelte";
  import SelectRegion from "./SelectRegion.svelte";

  export let searchedCountry, selectedRegion, theme;

  function handleSubmit(e) {
    e.preventDefault();
  }
</script>

<style>
  form {
    display: flex;
    margin-top: 2.5rem;
    width: 100%;
    max-width: var(--max-width);
  }
</style>

<Container>
  <form on:submit={handleSubmit}>
    <CountrySearch bind:searchedCountry {theme} />
    <SelectRegion bind:selectedRegion />
  </form>
</Container>
