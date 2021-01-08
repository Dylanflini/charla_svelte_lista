<script>
  import Title from "./Title.svelte";
  import DarkMode from "./DarkMode.svelte";

  export let theme;
</script>

<style>
  nav {
    background: var(--second-background);
    box-shadow: var(--boxshadow);
    display: flex;
    justify-content: center;
    padding: 0 2%;
  }
  ul {
    margin: 0;
    padding: 0;
    list-style: none;
    display: flex;
    align-items: center;
    width: 100%;
    max-width: var(--max-width);
  }
</style>

<nav>
  <ul>
    <Title>Where in the world?</Title>
    <DarkMode bind:theme />
  </ul>
</nav>
