<script>
  import BoxRed from "./BoxRed.svelte";
  $: status = "Waiting";
  function handleEventFromRed(event) {
    status = "Reached!";
    setTimeout(() => {
      status = "Finished!";
    }, event.detail.time);
  }
</script>
<div>
<span>BOX YELLOW {status}</span>
  <BoxRed on:toYellow={handleEventFromRed} />
</div>
<style lang="scss">
  div {
    border: 2px solid #444;
    padding: 2em;
  }
  span {
    font-size: 20px;
    font-weight: 700;
    color: rgb(255, 136, 0);
  }
</style>