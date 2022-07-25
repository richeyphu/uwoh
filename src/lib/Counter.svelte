<script>
  export let counter = 0
  const audio = new Audio();
  const segg = () => {
    addOneSeg();
    uwoh();
  }
  const uwoh = async () => {
    audio.src = "../../../public/segg.wav";
    audio.play();
  }
  const addOneSeg = () => {
    counter += 1;
  }
</script>

<audio preload="auto">
  <source src="../../../public/segg.wav" type="audio/wav">
</audio>

<button on:click={segg}>
  😭🗣
</button>
