<script lang="ts">
	// InterestForm: collects name, email, an optional reason, and email-updates consent, then posts
	// to Formspree via fetch (Accept: application/json) for an inline result.
	// Falls back to a native form POST when JavaScript is unavailable.
	import Button from './Button.svelte';

	const endpoint = 'https://formspree.io/f/mykqevwq';

	type Status = 'idle' | 'submitting' | 'success' | 'error';
	let status = $state<Status>('idle');
	let errorMessage = $state('');

	async function handleSubmit(event: SubmitEvent) {
		event.preventDefault();
		const form = event.currentTarget as HTMLFormElement;
		const data = new FormData(form);

		status = 'submitting';
		errorMessage = '';

		try {
			const response = await fetch(endpoint, {
				method: 'POST',
				body: data,
				headers: { Accept: 'application/json' }
			});

			if (response.ok) {
				status = 'success';
				form.reset();
				return;
			}

			const result = await response.json().catch(() => null);
			errorMessage =
				result?.errors?.map((e: { message: string }) => e.message).join(', ') ??
				'Something went wrong. Please try again.';
			status = 'error';
		} catch {
			errorMessage = 'Network error. Please check your connection and try again.';
			status = 'error';
		}
	}
</script>

{#if status === 'success'}
	<div class="border-2 border-gunmetal-900 bg-aquamarine-300 p-6 shadow-brutal-lg">
		<p class="text-xl font-extrabold text-gunmetal-900">Thanks — you're on the list! 🎉</p>
		<p class="mt-1 text-gunmetal-800">We'll be in touch soon.</p>
		<button
			class="mt-4 font-bold text-gunmetal-900 underline underline-offset-4"
			onclick={() => (status = 'idle')}
		>
			Submit another response
		</button>
	</div>
{:else}
	<form
		action={endpoint}
		method="POST"
		onsubmit={handleSubmit}
		class="flex flex-col gap-4"
		novalidate
	>
		<div class="flex flex-col gap-1">
			<label for="if-name" class="font-bold text-gunmetal-900">Name</label>
			<input
				id="if-name"
				name="name"
				type="text"
				autocomplete="name"
				class="border-2 border-gunmetal-900 bg-gunmetal-50 px-3 py-2.5 shadow-brutal-sm focus:outline-2 focus:outline-offset-2 focus:outline-vivid-orchid-500"
			/>
		</div>

		<div class="flex flex-col gap-1">
			<label for="if-email" class="font-bold text-gunmetal-900">Email <span class="text-fiery-terracotta-600">*</span></label>
			<input
				id="if-email"
				name="email"
				type="email"
				required
				autocomplete="email"
				class="border-2 border-gunmetal-900 bg-gunmetal-50 px-3 py-2.5 shadow-brutal-sm focus:outline-2 focus:outline-offset-2 focus:outline-vivid-orchid-500"
			/>
		</div>

		<div class="flex flex-col gap-1">
			<label for="if-reason" class="font-bold text-gunmetal-900">
				Why are you interested? <span class="font-normal text-gunmetal-500">(optional)</span>
			</label>
			<textarea
				id="if-reason"
				name="reason"
				rows="3"
				class="border-2 border-gunmetal-900 bg-gunmetal-50 px-3 py-2.5 shadow-brutal-sm focus:outline-2 focus:outline-offset-2 focus:outline-vivid-orchid-500"
			></textarea>
		</div>

		<label class="flex items-start gap-3">
			<input
				name="consent"
				type="checkbox"
				value="yes"
				class="mt-1 h-5 w-5 shrink-0 border-2 border-gunmetal-900 accent-aquamarine-500"
			/>
			<span class="text-gunmetal-800">I agree to receive email updates from openEMG.</span>
		</label>

		<!-- Honeypot anti-spam field (Formspree convention) -->
		<input type="text" name="_gotcha" tabindex="-1" autocomplete="off" class="hidden" aria-hidden="true" />

		{#if status === 'error'}
			<p class="border-2 border-fiery-terracotta-600 bg-fiery-terracotta-100 px-3 py-2 font-medium text-fiery-terracotta-800">
				{errorMessage}
			</p>
		{/if}

		<Button type="submit" variant="primary" disabled={status === 'submitting'} class="w-full sm:w-auto">
			{status === 'submitting' ? 'Sending…' : 'Join the list'}
		</Button>
	</form>
{/if}
