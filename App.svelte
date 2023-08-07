<script>
	import BoxYellow from "./BoxYellow.svelte";
  const selectOptions = {
    "Waiting": 0,
    "Reached!": 2000,
    "Done!": 1000
  };
  let selectedOption = 0;
  let textAreaValue = 'AFSF';

  $: {
    console.log(textAreaValue)
  }
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

  <h3>Github repository <a href="https://github.com/amitht18/svelte-createEventDispatcher-demo" rel="noopener noreferrer" target="_blank">amitht18/svelte-createEventDispatcher-demo</a></h3>
  <select name="demoSelect" id="status" bind:value={selectedOption}>
    {#each Object.entries(selectOptions) as [key, value]}
      <option value={value}>{key}</option>
    {/each}
  </select>

  <textarea name="demoTextarea" id="nnnnn" bind:value={textAreaValue} cols="30" rows="10"></textarea>
  <div>{textAreaValue}</div>
</main>