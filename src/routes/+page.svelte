<script>
	import { fly } from 'svelte/transition';

	let show = $state(false);

	$effect(() => {
		show = true;
	});
</script>

<div class="flex h-full items-center justify-center dark:bg-zinc-950 dark:text-neutral-500">
	{#if show}
		<div in:fly={{ y: 20, duration: 700 }} class="flex flex-col items-center justify-center p-10">
			<div class="mb-2 text-base font-medium text-slate-950 dark:text-zinc-300">
				Migrating Components, Projects are Launching Soon!.
			</div>
			<span class="my-1 dark:text-orange-500">⌁</span>

			<div class="mb-2 text-center">
				<span class="text-sm font-medium text-slate-950 dark:text-zinc-500">Current Stack</span>

				<div class=" text-slate-700 dark:text-orange-500">Sveltekit • Tailwind4 • Cloudflare</div>
				<div class=" text-slate-700 dark:text-zinc-300">Prevoius: NextJS • Shadcn • StoryBook</div>
			</div>

			<span class="my-1 dark:text-orange-500">⌁</span>

			<div class="flex flex-col">
				<div class="w-full text-center text-sm font-medium text-slate-950 dark:text-zinc-500">
					2027 Projects
				</div>
				<div class="flex gap-4">
					<div>
						<a
							class="inline-flex w-full items-center justify-center text-center text-slate-700 underline dark:text-orange-500"
							href="/stackstore"
						>
							StackStore
						</a>
					</div>
					<div>
						<a
							class="inline-flex w-full items-center justify-center text-center text-slate-700 underline dark:text-orange-500"
							href="/metaful"
						>
							Metaful
						</a>
					</div>
				</div>
			</div>
		</div>
	{/if}
</div>
