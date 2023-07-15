<script>
  import BoxGreen from "./BoxGreen.svelte";
  import { createEventDispatcher } from "svelte";

  const dispatch = createEventDispatcher();
  function passToParent() {
    dispatch("toRed", {
      time: 2000
    });
  }
</script>
<div on:click={passToParent}>
<span>BOX GREEN, Click here!</span>
</div>
<style lang="scss">
  div {
    border: 2px solid #444;
    padding: 2em;
  }
  span {
    font-size: 20px;
    font-weight: 700;
    color: green;
  }
</style>