<script lang="ts">
	// Demos page: showcases EMG/EEG devices driving real computer use.
	import Card from '$lib/components/Card.svelte';
	import Button from '$lib/components/Button.svelte';
</script>

<svelte:head>
	<title>Demos · openEMG</title>
	<meta
		name="description"
		content="Watch openEMG's biosignal devices in action, including EEG-driven computer control with eye and facial movement."
	/>
</svelte:head>

<section class="mx-auto max-w-6xl px-4 py-16 sm:px-6 sm:py-20">
	<h1 class="text-4xl font-extrabold tracking-tight text-gunmetal-900 sm:text-5xl">Demos</h1>
	<p class="mt-3 max-w-2xl text-lg text-gunmetal-700">
		Real devices, real control. Here's our technology in action.
	</p>

	<div class="mt-10 max-w-3xl">
		<Card bg="bg-lavender-blush-100">
			<h2 class="text-2xl font-extrabold text-gunmetal-900">EEG for computer use</h2>
			<p class="mt-2 text-gunmetal-800">
				Controlling a computer with eye and facial movement, read through EEG.
			</p>
			<div
				class="mt-5 aspect-video w-full overflow-hidden border-2 border-gunmetal-900 shadow-brutal"
			>
				<iframe
					class="h-full w-full"
					src="https://www.youtube.com/embed/xK5VmC4PBDk"
					title="EEG for computer use with eye and facial movement"
					allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture; web-share"
					referrerpolicy="strict-origin-when-cross-origin"
					allowfullscreen
				></iframe>
			</div>
		</Card>
	</div>

	<div class="mt-10">
		<Button href="/#contact" variant="primary">Want a demo for your use case? →</Button>
	</div>
</section>
