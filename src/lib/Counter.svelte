<script>
  export let counter = 0
  
  const segg = () => {
    addOneSeg();
    uwoh();
  }
  const uwoh = () => {
    const audio = new Audio();
    audio.src = "/segg.wav";
    audio.play();
  }
  const addOneSeg = () => {
    counter += 1;
  }
</script>

<button on:click={segg}>
  😭🗣
</button>
