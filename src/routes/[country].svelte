<script>
  import Nav from "$components/Nav.svelte";
  import { onMount } from "svelte";
  import Body from "$components/Body.svelte";
  import BorderCountries from "../components/BorderCountries.svelte";
  import Container from "../components/Container.svelte";
  import BasicCountryData from "../components/BasicCountryData.svelte";
  import Flag from "../components/Flag.svelte";

  let theme = {},
    country = { name: " " };

  const URL = "https://restcountries.eu/rest/v2/name/";
  // const URL_CODE = "https://restcountries.eu/rest/v2/alpha/";

  onMount(() => {
    console.log(location.pathname);
    country.name = location.pathname.replace(/^\//, "");

    (async () => {
      const response = await fetch(URL + country.name);
      [country] = await response.json();
    })();
  });
</script>

<style>
  section {
    margin-top: 4rem;
    display: flex;
    justify-content: center;
    padding: 0 2%;
  }

  div {
    margin: auto 0;
    flex-wrap: wrap;
    flex-grow: 1;
    margin-left: 2rem;
  }
</style>

<Body {theme}>
  <Nav bind:theme />
  <section>
    <Container>
      <Flag src={country.flag} alt={`Bandera de ${country.name}`} />

      <div>
        <BasicCountryData {country} />
        <BorderCountries borders={[country.borders]} />
      </div>
    </Container>
  </section>
</Body>
