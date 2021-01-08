<script>
  export let country;
</script>

<style>
  div {
    display: flex;
    align-items: flex-end;
    height: 80%;
    flex-wrap: wrap;
  }

  h1,
  ul {
    color: var(--color);
    opacity: var(--text-opacity);
  }

  ul {
    list-style: none;
    padding: 0;
    margin: 0;
    text-align: left;
    margin-right: 1rem;
  }

  li {
    list-style: none;
    margin: 1rem 0;
  }
</style>

<div>
  <ul>
    <h1>{country.name}</h1>
    <li><strong>Native Name: </strong>{country.nativeName}</li>
    <li><strong>Population: </strong>{country.population}</li>
    <li><strong>Top Level Domain: </strong>{country.topLevelDomain}</li>
  </ul>

  <ul>
    <li><strong>Region: </strong>{country.region}</li>
    <li><strong>Sub Region: </strong>{country.subregion}</li>
    <li><strong>Capital: </strong>{country.capital}</li>
  </ul>
</div>
