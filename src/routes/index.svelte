<script>
	import Nav from "$components/Nav.svelte";
	import CountriesContainer from "$components/CountriesContainer.svelte";
	import Form from "$components/Form.svelte";
	import Body from "../components/Body.svelte";

	let searchedCountry = "",
		selectedRegion,
		theme = {};

</script>

<Body {theme}>
	<Nav bind:theme />
	<Form bind:searchedCountry bind:selectedRegion {theme} />
	<CountriesContainer {searchedCountry} {selectedRegion} />
</Body>
