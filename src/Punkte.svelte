<script>
  export let insFragen;
  export let plusPunkte;
  export let minusPunkte;
</script>

<div class="insFragen">
  Antworten: <span class="insFragenZahl">{insFragen}</span>
</div>
<div class="plusPunkte">
  Richtig:
  <span class="plusPunkteZahl">{plusPunkte}</span>
</div>
<div class="minusPunkte">
  Falsch:
  <span class="minusPunkteZahl">{minusPunkte}</span>
</div>

<style>
  .insFragen {
    margin: 15px;
  }
  .minusPunkte,
  .plusPunkte {
    margin: 15px;
    display: inline;
  }
  .plusPunkteZahl,
  .minusPunkteZahl {
    font-weight: bold;
  }

  .plusPunkteZahl {
    color: #22e358;
  }
  .minusPunkteZahl {
    color: #f65a5a;
  }
</style>
