<script lang="ts">
	// Footer: book-a-meeting CTA plus copyright.
	import Button from './Button.svelte';

	const bookingUrl =
		'https://calendar.google.com/calendar/u/0/appointments/schedules/AcZssZ31U1ZeaAnwogXmoWvbnBHSB2HAX7HI5UH6qFAuOLnK_aWvDUA9B6b_G20DoPSqYuGFtHVL6FRL';

	const year = new Date().getFullYear();
</script>

<footer class="mt-20 border-t-2 border-gunmetal-900 bg-gunmetal-900 text-gunmetal-50">
	<div
		class="mx-auto flex max-w-6xl flex-col items-start gap-6 px-4 py-12 sm:px-6 md:flex-row md:items-center md:justify-between"
	>
		<div>
			<p class="text-2xl font-extrabold tracking-tight">Ready to build something accessible?</p>
			<p class="mt-1 text-gunmetal-300">Book a meeting and tell us what you need.</p>
		</div>
		<Button rel="noopener noreferrer" target="_blank" href={bookingUrl} variant="primary" class="shrink-0">Book a meeting →</Button>
	</div>
	<div class="border-t-2 border-gunmetal-700 px-4 py-4 text-sm text-gunmetal-400 sm:px-6">
		© {year} openEMG · Accessibility tech for computer use
	</div>
</footer>
