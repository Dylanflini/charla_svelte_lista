<script>
  import A from "./A.svelte";
</script>

<style>
  h1 {
    letter-spacing: 0.12rem;
    color: var(--color);
  }
</style>

<li>
  <A href="/" rel="noreferrer noopener">
    <h1>
      <slot />
    </h1>
  </A>
</li>
