<script>
  export let href, rel;
</script>

<style>
  a {
    text-decoration: none;
    color: var(--color);
  }
</style>

<a {href} {rel}>
  <slot />
</a>
