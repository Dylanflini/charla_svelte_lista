<script>
  import A from "./A.svelte";

  export let name, src, alt, population, region, capital;
</script>

<style>
  h2,
  ul {
    opacity: var(--text-opacity);
  }

  h2 {
    text-align: center;
  }

  ul {
    list-style: none;
    padding: 0;
    margin: 0 0 1rem 1rem;
    text-align: left;
  }

  img {
    width: 100%;
    height: 150px;
    object-fit: cover;
    border-top-left-radius: 4px;
    border-top-right-radius: 4px;
  }
</style>

<A href={'/' + name} rel="noreferrer noopener">
  <img {src} {alt} />
  <h2>{name}</h2>
  <ul>
    <li><strong>Population: </strong>{population}</li>
    <li><strong>Region: </strong>{region}</li>
    <li><strong>Capital: </strong>{capital}</li>
  </ul>
</A>
