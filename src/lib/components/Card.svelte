<script lang="ts">
	// Card: bordered, hard-shadowed container for grouping section content.
	import type { Snippet } from 'svelte';

	let {
		class: extraClass = '',
		bg = 'bg-gunmetal-50',
		children
	}: {
		class?: string;
		bg?: string;
		children: Snippet;
	} = $props();
</script>

<div class="border-2 border-gunmetal-900 shadow-brutal-lg p-6 sm:p-8 {bg} {extraClass}">
	{@render children()}
</div>
