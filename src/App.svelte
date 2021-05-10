<script>
  import Timer from "./Timer.svelte";
  import HowTo from "./HowTo.svelte";

  let audio;

  function timerEnds(e) {
    audio.play();
  }
</script>

<h1>Handwashing app</h1>

<!-- Timer component -->
<Timer on:end={timerEnds} />

<!-- HowTo component -->
<HowTo />

<audio bind:this={audio} src="yeah.mp3" />

<style>
  h1 {
    text-align: center;
  }
</style>
