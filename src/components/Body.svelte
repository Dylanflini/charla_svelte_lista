<script>
  export let theme;
</script>

<style>
  body {
    font-family: system-ui;
    background: var(--background);
    min-height: 100vh;
    --max-width: 1200px;
    --outline: solid 2px red;
    --text-opacity: 0.8;
    /* transition: color 1s; */
  }
</style>

<body
  style="--background: {theme.background}; --second-background: {theme.secondBackground}; --color: {theme.color}; --boxshadow: {theme.boxshadow};">
  <slot />
</body>
