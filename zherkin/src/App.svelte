<script>
    import Feature from './lib/Feature.svelte'

    async function getData() {
        const res = await fetch(`/gherkin-contract-example.json`)
        const json = await res.json()

        if (res.ok) {
            return json
        } else {
            throw new Error(json)
        }
    }

    let data = getData()
</script>

<main>
    {#await data}
        <p>...loading</p>
    {:then features}
        {#each features as feature}
            <Feature {feature} />
        {/each}
    {:catch error}
        <p style="color: red">{error.message}</p>
    {/await}
</main>

<style>
    main {
        /* text-align: center; */
        /* padding: 1em; */
        /* margin: 0 auto; */
    }
</style>
