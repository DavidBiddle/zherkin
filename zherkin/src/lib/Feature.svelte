<script>
    import Scenario from './Scenario.svelte'
    export let feature
</script>

<section>
    <h1>{feature.name}</h1>

    {#each feature.scenarios as scenario}
        <Scenario {scenario} />
    {/each}
</section>

<style>
    section {
        font-family: sans-serif;
    }
</style>
