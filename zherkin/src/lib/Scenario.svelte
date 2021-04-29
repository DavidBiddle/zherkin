<script>
    import Step from './Step.svelte'
    export let scenario
</script>

<h3>{scenario.name}</h3>

{#if scenario?.examples}
    {#each scenario.examples as example}
        <ul>
            {#each scenario.steps as step}
                <Step {step} {example} />
            {/each}
        </ul>
    {/each}
{:else}
    <ul>
        {#each scenario.steps as step}
            <Step {step} />
        {/each}
    </ul>
{/if}

<style>
</style>
