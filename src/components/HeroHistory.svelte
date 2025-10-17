<script>
  export let heroInfo;
</script>

<div class="yourHistoryClass">
  <h3>Votre histoire :</h3>
  <div class="yourHistory">
    <label for="message">📜Il était une fois 𓂃🖊</label>
    <textarea
      class="textHisory"
      bind:value={heroInfo.histoire}
      placeholder="..."
    ></textarea>
  </div>
</div>
