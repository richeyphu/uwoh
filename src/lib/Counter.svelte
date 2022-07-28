<script lang="ts">
  export let counter = { local: 0, global: 0 };

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
    counter.local += 1;
    // counter.global += 1;
  };
  const saveSegg = () => {
    if (typeof window !== "undefined") {
      localStorage.setItem("seg", counter.local.toString());
    }
  };
  (function loadSegg() {
    if (typeof window !== "undefined") {
      const stored = localStorage.getItem("seg");
      if (stored) {
        counter.local = parseInt(stored);
      }
    }
    let loadWorldSegg;
    (loadWorldSegg = () => {
      const xhr = new XMLHttpRequest();
      xhr.open("GET", "https://api.countapi.xyz/get/uwoh.vercel.app/segg");
      xhr.responseType = "json";
      xhr.onload = function () {
        counter.global = this.response.value;
      };
      xhr.send();
    })();
    setInterval(function () {
      loadWorldSegg();
    }, 1337);
  })();
  const countSegg = () => {
    const xhr = new XMLHttpRequest();
    xhr.open("GET", "https://api.countapi.xyz/hit/uwoh.vercel.app/segg");
    (() => {
      xhr.responseType = "json";
      xhr.onload = function () {
        counter.global = this.response.value;
      };
    })();
    xhr.send();
  };
</script>

<button on:click={segg}> 😭🗣 </button>
