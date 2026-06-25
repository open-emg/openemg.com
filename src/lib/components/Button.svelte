<script lang="ts">
	// Button: neobrutalism action element. Renders an <a> when `href` is set,
	// otherwise a <button>. Hard offset shadow that collapses on press.
	import type { Snippet } from 'svelte';

	type Variant = 'primary' | 'accent' | 'dark' | 'ghost';

	let {
		href,
		type = 'button',
		variant = 'primary',
		disabled = false,
		class: extraClass = '',
		children,
		...rest
	}: {
		href?: string;
		type?: 'button' | 'submit' | 'reset';
		variant?: Variant;
		disabled?: boolean;
		class?: string;
		children: Snippet;
		[key: string]: unknown;
	} = $props();

	const variants: Record<Variant, string> = {
		primary: 'bg-aquamarine-400 text-gunmetal-900',
		accent: 'bg-fiery-terracotta-400 text-gunmetal-900',
		dark: 'bg-gunmetal-900 text-aquamarine-300',
		ghost: 'bg-gunmetal-50 text-gunmetal-900'
	};

	const base =
		'inline-flex items-center justify-center gap-2 border-2 border-gunmetal-900 px-5 py-2.5 ' +
		'font-bold tracking-tight shadow-brutal transition-all duration-100 ' +
		'hover:-translate-x-0.5 hover:-translate-y-0.5 hover:shadow-brutal-lg ' +
		'active:translate-x-0 active:translate-y-0 active:shadow-brutal-sm ' +
		'focus-visible:outline-2 focus-visible:outline-offset-2 focus-visible:outline-vivid-orchid-500 ' +
		'disabled:cursor-not-allowed disabled:opacity-60 disabled:shadow-brutal disabled:translate-x-0 disabled:translate-y-0';
</script>

{#if href}
	<a {href} class="{base} {variants[variant]} {extraClass}" {...rest}>
		{@render children()}
	</a>
{:else}
	<button {type} {disabled} class="{base} {variants[variant]} {extraClass}" {...rest}>
		{@render children()}
	</button>
{/if}
