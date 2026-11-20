<script>
	import { resolve } from '$app/paths';
	import { fly } from 'svelte/transition';

	let animationState = $state(false);

	$effect(() => {
		animationState = true;
	});
</script>

{#if animationState}
	<main
		in:fly={{ y: 20, duration: 700 }}
		class="flex flex-col gap-20 p-11 text-base text-slate-800 dark:text-zinc-300"
	>
		<div>
			<p class="text-5xl font-semibold text-slate-950 dark:text-zinc-100">Stack Store UX Revamp</p>
			<p class="mt-4 text-3xl leading-11">
				As part of a recent UX initiative, I collaborated with a local e-commerce platform to audit
				the existing experience and solve critical usability bottlenecks. This case study highlights
				key friction points discovered during the audit and details the targeted design solutions
				implemented to optimize the overall user journey.
			</p>
		</div>
		<div>
			<p class="text-xl font-semibold">Reducing Card Clutter & Simplifying Entry Points</p>
			<p class="text-lg">
				To reduce cognitive overload, product cards dynamically adapt to each step of the user
				flow—displaying only the essential information and actions required for that specific stage.
			</p>
		</div>

		<div>
			<div class="grid grid-cols-[repeat(auto-fit,minmax(500px,1fr))] gap-12">
				<div
					class="flex h-200 items-center justify-center rounded-md dark:border-zinc-200 dark:bg-zinc-900/20"
				>
					card 1
				</div>
				<div
					class="flex h-200 items-center justify-center rounded-md dark:border-zinc-200 dark:bg-zinc-900/20"
				>
					card 2
				</div>
				<div
					class="flex h-200 items-center justify-center rounded-md dark:border-zinc-200 dark:bg-zinc-900/20"
				>
					card 3
				</div>
			</div>
		</div>
	</main>
{/if}
