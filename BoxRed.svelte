<script>
  import { createEventDispatcher } from "svelte";
  import BoxGreen from "./BoxGreen.svelte";

  const dispatch = createEventDispatcher();
  $: status = "Waiting";

  function handleEventFromGreen(event) {
    console.log("EVEEV", event);
    status = "Reached!";
    setTimeout(() => {
      dispatch("toYellow", event.detail);
      status = "Done!";
    }, event.detail.time);
  }
</script>
<div>
  <span>BOX RED {status}</span>
  <BoxGreen on:toRed={handleEventFromGreen} />
</div>
<style lang="scss">
  div {
    border: 2px solid #444;
    padding: 2em;
  }
  span {
    font-size: 20px;
    font-weight: 700;
    color: red;
  }
</style>