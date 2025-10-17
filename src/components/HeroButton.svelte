<script>
  export let ficheVisible;
  import { createEventDispatcher } from "svelte";
  const dispatch = createEventDispatcher();

  function handleClick() {
    dispatch("random");
  }
</script>

<div class="buttonRandom">
  <button class:click-button={ficheVisible} on:click={handleClick}>Votre Héros</button>
</div>
