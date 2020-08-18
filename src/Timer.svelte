<script>
    import ProgressBar from './ProgressBar.svelte';
    import { createEventDispatcher } from "svelte";

    const totalSeconds = 20;
    let secondLeft = totalSeconds;
    let isRunning = false;
    $: progress = 100 - Math.ceil(secondLeft / totalSeconds * 100);
    const dispatch = createEventDispatcher();
    function startTimer() {
            isRunning = !isRunning;
            dispatch("start", "start timer");
            const timer = setInterval(() => {
                if (secondLeft > 0) {
                    secondLeft --;
                } else {
                    clearInterval(timer);
                    secondLeft = totalSeconds;
                    isRunning = !isRunning;
                    dispatch("end", "end timer");
                    return;
                }
            }, 1000);
    };
</script>
<style>
    h2 {
        margin: 0;
    }
    .start {
        background-color: deeppink;
        width: 100%;
        height: 4em;
        margin: 10px 0;
        cursor: pointer;
    }
    .start[disabled] {
        background-color: gray;
        cursor: not-allowed;
    }
</style>
<div bp="grid">
    <h2 bp="offset-5@md 4@md 12@sm">Seconds Left: {secondLeft}</h2>
</div>
<ProgressBar progress={progress}></ProgressBar>
<div bp="grid">
    <button class="start" bp="offset-5@md 4@md 12@sm" on:click={startTimer} disabled={isRunning}><strong>Start Washing Hands!</strong></button>
</div>
