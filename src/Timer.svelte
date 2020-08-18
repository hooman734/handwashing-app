<script>
    import ProgressBar from './ProgressBar.svelte';
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
</style>
<div bp="grid">
    <h2 bp="offset-5@md 4@md 12@sm">Seconds Left:</h2>
</div>
<ProgressBar></ProgressBar>
<div bp="grid">
    <button class="start" bp="offset-5@md 4@md 12@sm">Start</button>
</div>
