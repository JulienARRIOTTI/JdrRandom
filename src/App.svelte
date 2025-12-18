<script>

  import './assets/style.css';
  import bannier from '../public/image/bannierJDR.png';

  import HeroButton from "./components/HeroButton.svelte";
  import HeroStats from "./components/HeroStats.svelte";
  import HeroForm from "./components/HeroForm.svelte";
  import HeroHistory from "./components/HeroHistory.svelte";

  // === Données des classes ===
  const classes = [
    { nom: "🏹Archer", stats: { Force: 1, Dextérité: 4, Charisme: 3, Intelligence: 2, Constitution: 1, Sagesse: 1 } },
    { nom: "⚔️Guerrier", stats: { Force: 4, Dextérité: 2, Charisme: 1, Intelligence: 1, Constitution: 3, Sagesse: 1 } },
    { nom: "🪄Magicien", stats: { Force: 0, Dextérité: 2, Charisme: 2, Intelligence: 4, Constitution: 0, Sagesse: 4 } },
    { nom: "🗡️Voleur", stats: { Force: 2, Dextérité: 5, Charisme: 2, Intelligence: 1, Constitution: 0, Sagesse: 2 } },
    { nom: "🛡️Tank", stats: { Force: 3, Dextérité: 1, Charisme: 1, Intelligence: 0, Constitution: 5, Sagesse: 2 } },
    { nom: "🐺Druide", stats: { Force: 3, Dextérité: 1, Charisme: 0, Intelligence: 2, Constitution: 3, Sagesse: 3 } },
    { nom: "🧪Alchimiste", stats: { Force: 2, Dextérité: 1, Charisme: 1, Intelligence: 4, Constitution: 1, Sagesse: 2 } },
  ];

  let ficheVisible = false;
  let hero = null;
  let heroInfo = { name: "", origine: "", weapon: "", weaponSecond: "", histoire: "" };

  function randomHero() {
    if (ficheVisible) {
      hero = null;
      ficheVisible = false;
    } else {
      hero = classes[Math.floor(Math.random() * classes.length)];
      ficheVisible = true;
    }
  }
</script>

<header class="banner" style="background: url({bannier}) no-repeat; background-size: cover; background-position: center;">
  <h1>JEUX De RÔLE</h1>
</header>

<main>
  <div class="intro">
    <h2>
      Pour pas de prise de tête sur le choix de la classe de votre héros, voici un petit bouton
      qui vous le donnera en "Random" et les stats définies.
    </h2>
  </div>

  <HeroButton on:random={randomHero} {ficheVisible} />

  <div class="table">
    <HeroStats {hero} {ficheVisible} />
    <HeroForm bind:heroInfo={heroInfo} />
  </div>
</main>

<footer>
  <HeroHistory bind:heroInfo={heroInfo} />
</footer>

<style>
  @import "./assets/style.css";
</style>
