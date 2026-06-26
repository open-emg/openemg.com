<script lang="ts">
	// Landing page: mission, technology overview, offering, and interest form.
	import Button from '$lib/components/Button.svelte';
	import Card from '$lib/components/Card.svelte';
	import InterestForm from '$lib/components/InterestForm.svelte';
</script>

<svelte:head>
	<title>openEMG · EMG accessibility tech for computer use</title>
	<meta
		name="description"
		content="openEMG builds EMG and EEG devices that give people with disabilities agency over their computers and electronics."
	/>
</svelte:head>

<!-- Hero / Mission -->
<section class="bg-aquamarine-300">
	<div class="mx-auto max-w-6xl px-4 py-10 sm:px-6 sm:py-14">
		<h1 class="mt-6 max-w-3xl text-4xl font-extrabold leading-tight tracking-tight text-gunmetal-900 sm:text-6xl">
			We use EMG devices to promote agency.
		</h1>
		<p class="mt-6 max-w-2xl text-lg text-gunmetal-800 sm:text-xl">
			openEMG builds devices that read the body's own electrical signals, so people with
			disabilities can control computers and electronics on their own terms.
		</p>
		<div class="mt-8 flex flex-wrap gap-4">
			<Button href="#contact" variant="dark">Get in touch</Button>
			<Button href="/tech" variant="ghost">Explore the tech</Button>
		</div>
		<span
			class="inline-block border-2 border-gunmetal-900 bg-gunmetal-50 px-3 mt-5 py-1 text-sm font-bold shadow-brutal-sm"
		>
			Accessibility tech · Computer use
		</span>
	</div>
</section>

<!-- What is the technology -->
<section class="mx-auto max-w-6xl px-4 py-16 sm:px-6 sm:py-20">
	<h2 class="text-3xl font-extrabold tracking-tight text-gunmetal-900 sm:text-4xl">
		What is the technology?
	</h2>
	<p class="mt-3 max-w-2xl text-lg text-gunmetal-700">
		We work with biosignals: the tiny electrical voltages your body gives off when muscles and
		neurons fire, then turn them into reliable computer input.
	</p>

	<div class="mt-8 grid gap-6 md:grid-cols-2">
		<Card bg="bg-lavender-blush-100">
			<h3 class="text-2xl font-extrabold text-gunmetal-900">EMG</h3>
			<p class="mt-2 text-gunmetal-800">
				Electromyography reads muscle activity right from the surface of your skin, so even the faintest
				intentional movement can become a click, a gesture, or a keystroke.
			</p>
			<div class="mt-5">
				<Button href="/tech" variant="primary" class="px-4 py-2">Learn about Surface EMG →</Button>
			</div>
		</Card>

		<Card bg="bg-vivid-orchid-100">
			<h3 class="text-2xl font-extrabold text-gunmetal-900">EEG</h3>
			<p class="mt-2 text-gunmetal-800">
				Electroencephalography reads brain and facial-muscle signals. See it driving real computer
				control with eye and facial movement in our demos.
			</p>
			<div class="mt-5">
				<Button href="/demos" variant="accent" class="px-4 py-2">Watch the demos →</Button>
			</div>
		</Card>
	</div>
</section>

<!-- What we offer -->
<section class="bg-gunmetal-900 text-gunmetal-50">
	<div class="mx-auto max-w-6xl px-4 py-16 sm:px-6 sm:py-20">
		<h2 class="text-3xl font-extrabold tracking-tight sm:text-4xl">What we offer</h2>
		<p class="mt-3 max-w-2xl text-lg text-gunmetal-300">
			We do accessibility contracting. You tell us what's getting in the way, and we figure out a
			solution and build it.
		</p>

		<div class="mt-10 grid gap-6 md:grid-cols-3">
			<div class="border-2 border-aquamarine-400 bg-gunmetal-800 p-6">
				<span class="text-3xl font-black text-aquamarine-400">01</span>
				<h3 class="mt-2 text-xl font-bold">You describe the problem</h3>
				<p class="mt-2 text-gunmetal-300">Tell us what you're struggling to do with your devices.</p>
			</div>
			<div class="border-2 border-aquamarine-400 bg-gunmetal-800 p-6">
				<span class="text-3xl font-black text-aquamarine-400">02</span>
				<h3 class="mt-2 text-xl font-bold">We design a solution</h3>
				<p class="mt-2 text-gunmetal-300">We figure out the right EMG/EEG approach for your needs.</p>
			</div>
			<div class="border-2 border-aquamarine-400 bg-gunmetal-800 p-6">
				<span class="text-3xl font-black text-aquamarine-400">03</span>
				<h3 class="mt-2 text-xl font-bold">We build it</h3>
				<p class="mt-2 text-gunmetal-300">We make the device and get it working for you.</p>
			</div>
		</div>
	</div>
</section>

<!-- Interest form -->
<section id="contact" class="mx-auto max-w-6xl scroll-mt-20 px-4 py-16 sm:px-6 sm:py-20">
	<div class="grid gap-10 md:grid-cols-2">
		<div>
			<h2 class="text-3xl font-extrabold tracking-tight text-gunmetal-900 sm:text-4xl">
				Stay in the loop
			</h2>
			<p class="mt-3 text-lg text-gunmetal-700">
				Leave your details and we'll keep you posted on what we're building. Prefer to talk? Book a
				meeting from the footer below.
			</p>
		</div>
		<Card bg="bg-gunmetal-50">
			<InterestForm />
		</Card>
	</div>
</section>
