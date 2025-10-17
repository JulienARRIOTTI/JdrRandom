<script>
  export let heroInfo;
  const colorMap = {
    Orc: '#4b8f3b', Elf: '#3b5998', Humain: '#e2c275', Nain: '#a67c52',
    Arc: '#4b8f3b', Épées: '#3b5998', Hache: '#e2c275', Bouclier: '#a67c52',
    Dague: '#5c198b', Couteau: '#A60808', Baguette: '#A61192',
    'Épées courte': '#4b8f3b', Marteau: '#221A6B', Magie: '#e2c275'
  };
  const defaultColor = '#1e5657';
</script>

<div class="raceHistory">
  <h4>YOUR HERO</h4>

  <input
    class="nameHeroBox"
    bind:value={heroInfo.name}
    placeholder="📜Votre Nom"
  />

  <p>Votre race :</p>
  <select
    class="origine"
    bind:value={heroInfo.origine}
    style="background: {colorMap[heroInfo.origine] || defaultColor}"
  >
    <option value="" disabled selected hidden>📜Tes Origines</option>
    <option value="Orc">Orc 🧌</option>
    <option value="Elf">Elf 🧝</option>
    <option value="Humain">Humain 🧝🏻‍♂️</option>
    <option value="Nain">Nain 🤏</option>
  </select>

  <select
    class="weapon"
    bind:value={heroInfo.weapon}
    style="background: {colorMap[heroInfo.weapon] || defaultColor}"
  >
    <option value="" disabled selected hidden>🗃️Ton Arme</option>
    <option value="Arc">🏹 Arc</option>
    <option value="Épées">⚔️ Épées</option>
    <option value="Hache">🪓 Hache</option>
    <option value="Bouclier">🛡️ Bouclier</option>
    <option value="Dague">🗡️ Dague</option>
    <option value="Couteau">🔪 Couteau</option>
    <option value="Baguette">🪄 Baguette</option>
  </select>

  <select
    class="weaponSecond"
    bind:value={heroInfo.weaponSecond}
    style="background: {colorMap[heroInfo.weaponSecond] || defaultColor}"
  >
    <option value="" disabled selected hidden>🗃️Arme secondaire</option>
    <option value="Épées courte">⚔️ Épée courte</option>
    <option value="Marteau">🔨 Marteau</option>
    <option value="Dague">🗡️ Dague</option>
    <option value="Couteau">🔪 Couteau</option>
    <option value="Bouclier">🛡️ Bouclier</option>
    <option value="Magie">✨ Magie</option>
  </select>
</div>
