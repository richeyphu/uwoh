<script lang="ts">
  export let counter = 0;

  const segg = () => {
    addOneSegg();
    uwoh();
    saveSegg();
    countSegg();
  };
  const uwoh = () => {
    const audio = new Audio();
    audio.src = "/segg.wav";
    audio.play();
  };
  const addOneSegg = () => {
    counter += 1;
  };
  const saveSegg = () => {
    if (typeof window !== "undefined") {
      localStorage.setItem("seg", counter.toString());
    }
  };
  (function loadSegg() {
    if (typeof window !== "undefined") {
      const stored = localStorage.getItem("seg");
      if (stored) {
        counter = parseInt(stored);
      }
    }
  })();
  const countSegg = () => {
    const xhr = new XMLHttpRequest();
    xhr.open("GET", "https://api.countapi.xyz/hit/uwoh.vercel.app/segg");
    // (() => {
    //   xhr.responseType = "json";
    //   xhr.onload = () => {
    //     alert(`This button has been clicked ${this.response.value} times!`);
    //   };
    // })();
    xhr.send();
  };
</script>

<button on:click={segg}> 😭🗣 </button>
