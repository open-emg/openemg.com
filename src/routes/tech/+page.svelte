<script lang="ts">
	// Tech page: explains the biosignal technology, starting with Surface EMG.
	import Card from '$lib/components/Card.svelte';
	import Button from '$lib/components/Button.svelte';

	import exampleImage from '$lib/assets/emg_demo.jpeg';
</script>

<svelte:head>
	<title>Technology · openEMG</title>
	<meta
		name="description"
		content="How openEMG turns biosignals into computer input, starting with surface electromyography (EMG)."
	/>
</svelte:head>

<section class="mx-auto max-w-6xl px-4 py-16 sm:px-6 sm:py-20">
	<h1 class="text-4xl font-extrabold tracking-tight text-gunmetal-900 sm:text-5xl">Technology</h1>
	<p class="mt-3 max-w-2xl text-lg text-gunmetal-700">
		We turn the body's electrical signals into reliable, accessible computer input.
	</p>

	<div class="mt-10">
		<Card bg="bg-gunmetal-50">
			<div class="grid gap-8 md:grid-cols-2 md:items-center">
				<div>
					<h2 class="text-2xl font-extrabold text-gunmetal-900 sm:text-3xl">Surface EMG</h2>
					<p class="mt-3 text-gunmetal-800">
						Surface electromyography (sEMG) measures the electrical activity muscles produce when
						they contract, using sensors that sit on your skin. No needles, no surgery. Because the
						signal appears the moment you <em>intend</em> to move, even small or partial movements can
						drive a cursor, trigger a click, or stand in for a key press.
					</p>
					<p class="mt-3 text-gunmetal-800">
						That makes sEMG a powerful, low-friction input channel for people for whom a standard
						mouse and keyboard don't work.
					</p>
					<div class="mt-6 flex flex-wrap gap-3">
						<Button
							href="https://en.wikipedia.org/wiki/Electromyography"
							variant="ghost"
							class="px-4 py-2"
							rel="noopener noreferrer"
							target="_blank"
						>
							Wikipedia: Electromyography ↗
						</Button>
						<Button
							href="https://pmc.ncbi.nlm.nih.gov/articles/PMC3821366/"
							variant="ghost"
							class="px-4 py-2"
							rel="noopener noreferrer"
							target="_blank"
						>
							Research paper ↗
						</Button>
					</div>
				</div>
				<div class="border-2 border-gunmetal-900 shadow-brutal overflow-hidden">
					<img
						src={exampleImage}
						alt="A surface EMG device reading muscle signals from the skin"
						class="h-full w-full object-cover"
					/>
				</div>
			</div>
		</Card>
	</div>

	<div class="mt-10">
		<Button href="/demos" variant="accent">See it in action →</Button>
	</div>
</section>
