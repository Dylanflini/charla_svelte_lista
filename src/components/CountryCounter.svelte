<script>
  import Container from "./Container.svelte";

  export let length;
</script>

<style>
  p {
    opacity: var(--text-opacity);
    padding-top: 1rem;
    color: var(--color);
    font-family: system-ui;
    width: 100%;
    max-width: var(--max-width);
    padding: 0;
    margin: 2rem 0 0 0;
  }
</style>

<Container>
  <p><strong>Countries found: </strong>{length}</p>
</Container>
