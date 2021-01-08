<script context="module">
  export const FILTER_REGION_DEFAULT = "Filter By Region";
</script>

<script>
  export let selectedRegion = FILTER_REGION_DEFAULT;
</script>

<style>
  label,
  select {
    background: var(--second-background);
  }

  label {
    margin-left: auto;
    height: 2rem;
    border: 0;
    padding: 0.5rem;
    border-radius: 4px;
    box-shadow: var(--boxshadow);
  }

  label:focus-within {
    outline: var(--outline);
  }

  select {
    color: var(--color);
    border: 0;
    -webkit-appearance: none;
    outline: none;
    padding: 0.4rem;
    font-size: 1rem;
  }

  label:hover {
    cursor: pointer;
  }

  option {
    -webkit-appearance: none;
    background: chocolate;
  }
</style>

<label for="filter">
  <select bind:value={selectedRegion} name="filter" id="filter">
    <option>{FILTER_REGION_DEFAULT}</option>
    <option value="Africa">Africa</option>
    <option value="Americas">America</option>
    <option value="Asia">Asia</option>
    <option value="Europe">Europe</option>
    <option value="Oceania">Oceania</option>
  </select>
</label>
