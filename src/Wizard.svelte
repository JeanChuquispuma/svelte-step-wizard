<script>
    import { writable } from "svelte/store";
    import { setContext } from "svelte";

    export let initialStep = 0
    export let setStep = 0
    const step = writable(initialStep)

    $: $step = setStep;

    const nextStep = () => {
			$step += 1
	}
	const previousStep = () => {
		if ($step > 0) {
			$step -= 1	
		}
	}
    const getStep = () => {
        return $step
    }

    setContext('StepWizard', {
		step,
		nextStep,
		previousStep,
        getStep
	})
</script>

<slot nextStep={nextStep} previousStep={previousStep} setStep={setStep} getStep={$step}></slot>