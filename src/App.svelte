<script>
	import Timer from './Timer.svelte';
	import HowTo from './HowTo.svelte';

	let audio;

	function timerStart(e) {
		console.log(e);
		audio.play();
	}
	function timerEnds(e) {
		console.log(e);
		audio.pause();
	}
</script>
<style>
	h1, h3 {
		text-align: center;
	}
</style>
<h1>Handwashing App</h1>
<Timer on:end={timerEnds} on:start={timerStart}></Timer>
<HowTo></HowTo>
<h3>
	<a href="https://www.google.com/url?sa=i&url=https%3A%2F%2Fwww.agfa.com%2Fprinting%2Fnews%2Fwash-your-hands-signs%2F&psig=AOvVaw13X7BUTXKkIC6u8nXJts1J&ust=1597765173077000&source=images&cd=vfe&ved=0CAIQjRxqFwoTCLDR4KLJousCFQAAAAAdAAAAABAD">Picture Source</a>
	<br>
	<a href="https://freesound.org/people/straget/sounds/415053/">Sound Source</a>
</h3>

<audio bind:this={audio}>
	<source src="flow-sound.wav"/>
</audio>