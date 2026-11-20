<script>
	import { resolve } from '$app/paths';
	import { fly } from 'svelte/transition';

	let show = $state(false);

	$effect(() => {
		show = true;
	});
</script>

<div
	class="flex h-full items-center justify-center bg-slate-100 dark:bg-zinc-950 dark:text-neutral-500"
>
	{#if show}
		<div in:fly={{ y: 20, duration: 700 }} class="flex flex-col items-center justify-center p-10">
			<div class="mb-2 text-base font-medium text-neutral-950 dark:text-zinc-300">
				Work In Progress, Projects are Launching Soon!.
			</div>
			<span class="my-1 dark:text-orange-500">⌁</span>

			<div class="mb-2 text-center">
				<span class="text-sm font-medium text-neutral-950 dark:text-zinc-300">Current Stack</span>

				<div class="text-sm text-blue-700 dark:text-orange-500">
					Sveltekit • Tailwind4 • cloudflare
				</div>
				<div class="text-sm text-neutral-500 dark:text-zinc-400">
					Prevoius: NextJS • Shadcn • StoryBook
				</div>
			</div>

			<span class="my-1 dark:text-orange-500">⌁</span>
			<div class="mb-3 flex flex-col text-center">
				<span class="text-sm font-medium font-semibold text-neutral-950 dark:text-zinc-300"
					>Status</span
				>
				<div class="text-sm text-neutral-600 dark:text-zinc-400">
					Migrating component architecture
				</div>
			</div>

			<!-- <div>
				<a href="/projectone">Project Pne</a>
			</div> -->
		</div>
	{/if}
</div>
