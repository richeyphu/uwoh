<script lang="ts">
  export let counter = 0
  
  const segg = () => {
    addOneSeg();
    uwoh();
    saveSegg();
  }
  const uwoh = () => {
    const audio = new Audio();
    audio.src = "/segg.wav";
    audio.play();
  }
  const addOneSeg = () => {
    counter += 1;
  }
  const saveSegg = () => {
    if (typeof window !== "undefined") {
      localStorage.setItem("seg", counter.toString());
    }
  }
  const loadSegg = () => {
    if (typeof window !== "undefined") {
      const stored = localStorage.getItem("seg");
      if (stored) {
        counter = parseInt(stored);
      }
    }
  }
  loadSegg();
</script>

<button on:click={segg}>
  😭🗣
</button>
