<script lang="ts">
  import Counter from "./lib/Counter.svelte";
  let count = 0;
  $: seg = count;
</script>

<main>
  <h1>😭🆂🥚</h1>

  <div class="card">
    <Counter bind:counter={count} />
  </div>
  <p>
    🆂🥚 : {seg}
  </p>
</main>
