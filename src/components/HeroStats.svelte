<script>
  export let hero;
  export let ficheVisible;
</script>

<div class="statclass {hero?.nom}">
  {#if ficheVisible && hero}
    <h3>{hero.nom}</h3>
    {#each Object.entries(hero.stats) as [stat, value]}
      <div>{stat} : {value}</div>
    {/each}
  {:else}
    <h3>Stat</h3>
  {/if}
</div>
