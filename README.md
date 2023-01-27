# svelte-step-wizard

Step wizard component for Svelte

## Install
```bash
npm i svelte-step-wizard
```

## Example
```svelte
<script>
    import StepWizard from 'svelte-step-wizard'
    let current = 0
</script>

<button on:click={() => {
    current = 0
}}>
Return to step 0
</button>

<StepWizard setStep={current}>
    <StepWizard.Step num={0} let:nextStep let:getStep>
		<p>
			This is the first step.
		</p>
        <div>Step number: {getStep()} </div>
		<button on:click={nextStep}>
			Next Step	>
		</button>
	</StepWizard.Step>
    <StepWizard.Step num={1} let:previousStep let:nextStep let:getStep>
		<p>
			This is the Second step.
		</p>
        <div>Step number: {getStep()} </div>
		<button on:click={previousStep}>
			Go Back
		</button>
		<button on:click={nextStep}>
			Next Step	>
		</button>
	</StepWizard.Step>
	<StepWizard.Step num={2} let:previousStep let:getStep>
		<p>
			This is the Third step.
		</p>
        <div>Step number: {getStep()} </div>
		<button on:click={previousStep}>
			Go Back
		</button>
	</StepWizard.Step>
</StepWizard>
```
