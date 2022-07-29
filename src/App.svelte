<script lang="ts">
  import Counter from "./lib/Counter.svelte";
  let count = { local: 0, global: 0 };
  $: seg = count.local;
  $: worldSeg = count.global;
</script>

<main>
  <h1>😭🆂🥚</h1>

  <div class="card">
    <Counter bind:counter={count} />
  </div>
  <p>
    🆂🥚 : {seg.toLocaleString()}
  </p>
  <p>
    🌏 : {worldSeg.toLocaleString()}
  </p>
</main>
