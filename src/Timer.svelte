<script>
  import ProgressBar from "./ProgressBar.svelte";
  const totalSeconds = 20;

  let isRunning = false;
  let secondLeft = totalSeconds;

  $: progress = ((totalSeconds - secondLeft) / totalSeconds) * 100;

  function startTimer() {
    isRunning = true;
    const timer = setInterval(() => {
      secondLeft -= 1;

      if (secondLeft == 0) {
        clearInterval(timer);
        isRunning = false;
        secondLeft = totalSeconds;
      }
    }, 1000);
  }
</script>

<div bp="grid">
  <h2 bp="offset-5@md 4@md 12@sm">Seconds left:{secondLeft}</h2>
</div>

<ProgressBar {progress} />

<div bp="grid">
  <button
    bp="offset-5@md 4@md 12@sm"
    class="stretch primary"
    on:click={startTimer}
    disabled={isRunning}>Start</button
  >
</div>

<style>
  h2 {
    margin: 0;
  }
</style>
