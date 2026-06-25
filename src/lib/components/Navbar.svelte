<script lang="ts">
	// Navbar: sticky top navigation with logo and primary links.
	// Collapses to a toggled menu on small screens.
	import Button from './Button.svelte';

	const links = [
		{ label: 'Home', href: '/' },
		{ label: 'Tech', href: '/tech' },
		{ label: 'Demos', href: '/demos' }
	];

	let open = $state(false);

	function close() {
		open = false;
	}
</script>

<header class="sticky top-0 z-50 border-b-2 border-gunmetal-900 bg-aquamarine-300">
	<nav class="mx-auto flex max-w-6xl items-center justify-between px-4 py-3 sm:px-6">
		<a href="/" class="flex items-center gap-2" onclick={close}>
			<img src="/openemg.png" alt="openEMG logo" class="h-9 w-auto" />
			<span class="text-lg font-extrabold tracking-tight text-gunmetal-900">openEMG</span>
		</a>

		<!-- Desktop links -->
		<div class="hidden items-center gap-2 md:flex">
			{#each links as link (link.href)}
				<a
					href={link.href}
					class="border-2 border-transparent px-3 py-1.5 font-bold text-gunmetal-900 hover:border-gunmetal-900 hover:bg-gunmetal-50"
				>
					{link.label}
				</a>
			{/each}
			<Button href="/#contact" variant="accent" class="px-4 py-1.5">Contact</Button>
		</div>

		<!-- Mobile toggle -->
		<button
			class="flex h-10 w-10 items-center justify-center border-2 border-gunmetal-900 bg-gunmetal-50 shadow-brutal-sm md:hidden"
			aria-label={open ? 'Close menu' : 'Open menu'}
			aria-expanded={open}
			onclick={() => (open = !open)}
		>
			<span class="text-xl font-black leading-none">{open ? '✕' : '☰'}</span>
		</button>
	</nav>

	<!-- Mobile menu -->
	{#if open}
		<div class="border-t-2 border-gunmetal-900 bg-aquamarine-300 px-4 pb-4 md:hidden">
			<div class="flex flex-col gap-2 pt-2">
				{#each links as link (link.href)}
					<a
						href={link.href}
						onclick={close}
						class="border-2 border-gunmetal-900 bg-gunmetal-50 px-3 py-2 font-bold text-gunmetal-900 shadow-brutal-sm"
					>
						{link.label}
					</a>
				{/each}
				<Button href="/#contact" variant="accent" class="px-3 py-2">Contact</Button>
			</div>
		</div>
	{/if}
</header>
