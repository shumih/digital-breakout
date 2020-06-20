<style>
  main {
    position: relative;
    max-width: 56em;
    background-color: white;
    padding: 2em;
    margin: 0 auto;
    box-sizing: border-box;
  }
</style>

<script>
  import Drawer from "../components/Drawer.svelte";

  export let segment;
</script>

<Drawer>
  <slot />
</Drawer>
