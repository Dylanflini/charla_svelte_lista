<script>
  import { onMount } from "svelte";
  import Container from "./Container.svelte";
  import CountryCard from "./CountryCard.svelte";
  import CountryCounter from "./CountryCounter.svelte";
  import { FILTER_REGION_DEFAULT } from "./SelectRegion.svelte";

  export let searchedCountry, selectedRegion;

  let allCountries = [],
    countriesFound = [];

  const URL = "https://restcountries.eu/rest/v2/all";

  onMount(() => {
    console.log("render");
    (async () => {
      const response = await fetch(URL);
      allCountries = await response.json();
    })();
  });

  $: {
    countriesFound = allCountries.filter(({ name, region }) =>
      inputFilter(searchedCountry, selectedRegion, name, region)
    );
  }

  function inputFilter(searchedName, selectedRegion, name, region) {
    if (selectedRegion === FILTER_REGION_DEFAULT) {
      return includesName(name, searchedName);
    } else {
      return includesName(name, searchedName) && region === selectedRegion;
    }
  }

  const includesName = (name, searched) =>
    name.toLowerCase().includes(searched.toLowerCase());
</script>

<style>
  ul {
    margin: 0;
    padding: 0;
    list-style: none;
    background: var(--background);
    color: var(--color);
    min-height: 2vh;
    display: grid;
    grid-template-columns: repeat(auto-fill, minmax(220px, 1fr));
    grid-template-rows: repeat(4, min-content);
    grid-gap: 2rem;
    padding-top: 2.5rem;
    padding-bottom: 3.5rem;
    width: 100%;
    max-width: var(--max-width);
  }

  li {
    /* background: var(--secondBackground); */
    background: var(--second-background);
    margin: 0 auto;
    flex: 1 1 100%;
    border-radius: 4px;
    box-shadow: var(--boxshadow);
  }
</style>

<CountryCounter length={countriesFound.length} />
<Container>
  <ul>
    {#each countriesFound as { name, flag, population, region, capital }}
      <li>
        <CountryCard
          {name}
          src={flag}
          alt={`bandera de ${name}`}
          {population}
          {region}
          {capital} />
      </li>
    {/each}
  </ul>
</Container>
