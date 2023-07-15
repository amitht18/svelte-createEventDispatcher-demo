<script>
	import BoxYellow from "./BoxYellow.svelte";
</script>
<style>
  main {
    font-family: sans-serif;
    text-align: center;
  }
</style>
<main>
  <div>
  <h2>Demo createEventDispatcher</h2>
  <h3>Demo to show component event passing and handling in Svelte</h3>
  <span>
  Event starts from Green with wait time and passes to Red, Red listens and sends event to Yellow with same wait time. Finally handled at Green.
  </span>
  </div>
  <BoxYellow />
</main>