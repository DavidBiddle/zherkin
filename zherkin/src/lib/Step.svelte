<script>
    export let step
    export let example = []

    function replaceExamples(step) {
        return example.reduce((accumulator, currentValue) => {
            return accumulator.replace(
                `<${currentValue[0]}>`,
                `<em>${currentValue[1]}</em>`
            )
        }, step)
    }

    function makeFirstWordBold(step) {
        return step.replace(/^\s*\w+/, '<strong>$&</strong>')
    }

    $: processedStepName = makeFirstWordBold(replaceExamples(step))
</script>

<li>
    {@html processedStepName}
</li>

<style>
</style>
