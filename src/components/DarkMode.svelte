<script>
  import { afterUpdate, onDestroy, onMount } from "svelte";

  export let theme;

  let darkMode;

  const DARK_MODE_KEY = "darkMode";

  function handleClick() {
    darkMode ? (darkMode = false) : (darkMode = true);
  }

  const lightTheme = {
    name: "light",
    background: "rgb(250, 250, 250)",
    secondBackground: "rgb(255, 255, 255)",
    color: "black",
    boxshadow: "1px 1px 4px rgb(185, 185, 185)",
  };

  const darkTheme = {
    name: "dark",
    background: "rgb(35, 45, 53)",
    secondBackground: "rgb(45, 55, 66)",
    color: "white",
    boxshadow: "1px 1px 8px rgb(40, 40, 40)",
  };

  afterUpdate(() => {
    console.log("update - theme: ", theme);
    
    if (theme.name === "dark") {
      console.log("set item session");
      sessionStorage.setItem(DARK_MODE_KEY, true);
    }

    if (theme.name === "light") {
      console.log("remove item session");
      sessionStorage.removeItem(DARK_MODE_KEY);
    }
  });

  $: {
    console.log("dark mode: ", darkMode);
    if (darkMode !== undefined) {
      darkMode ? (theme = darkTheme) : (theme = lightTheme);
    }
  }

  onMount(() => {
    console.log("session: ", sessionStorage.getItem(DARK_MODE_KEY));
    sessionStorage.getItem(DARK_MODE_KEY)
      ? (darkMode = true)
      : (darkMode = false);
  });
</script>

<style>
  li {
    margin-left: auto;
  }

  button,
  button:active {
    color: var(--color);
  }

  button {
    display: flex;
    border: none;
    background: none;
    align-items: center;
    margin: 0;
    padding: 0;
    outline: none;
  }

  li:focus-within,
  button:hover {
    cursor: pointer;
    transform: scale(1.05);
  }
  li:focus-within {
    outline: var(--outline);
  }

  button:active {
    transform: translateY(2px) scale(1.05);
  }

  img {
    width: 2rem;
    margin-right: 5%;
  }
</style>

<li>
  <button on:click={handleClick}>
    {#if darkMode}
      <img src="sun.svg" alt="dark mode icon" />
      Light Mode
    {:else}<img src="dark-mode.svg" alt="dark mode icon" /> Dark Mode{/if}
  </button>
</li>
