<script>
  import ProgressBar from "./ProgressBar.svelte";
</script>

<div bp="grid">
  <h2 bp="offset-5@md 4@md 12@sm">Seconds left:</h2>
</div>

<ProgressBar />

<button class="stretch primary">Start</button>

<style>
  h2 {
    margin: 0;
  }
</style>
