<script>
  export let antwortText;
  export let pruefAntwort;
</script>

<button class="antwort" on:click={() => pruefAntwort(antwortText)}
  >{antwortText}</button
>

<style>
  button.antwort {
    background-color: white;
    border-radius: 5px;
    font-size: 24px;
    width: 100px;
    height: 50px;
    margin: 10px;
    cursor: pointer;
  }

  button.antwort:active {
    background-color: orange;
    color: white !important;
  }

  button.antwort:nth-child(1) {
    box-shadow: 0 0 10px #5484ff;
    border: 2px solid #5484ff;
    color: #5484ff;
  }
  button.antwort:nth-child(3) {
    box-shadow: 0 0 10px #f6ca2a;
    border: 2px solid #f6ca2a;
    color: #f6ca2a;
  }
  button.antwort:nth-child(2) {
    box-shadow: 0 0 10px #f65a5a;
    border: 2px solid #f65a5a;
    color: #f65a5a;
  }
</style>
