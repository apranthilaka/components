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
			<div class="mb-2 text-sm text-slate-950 dark:text-zinc-300">
				Migrating Components, Projects are Launching Soon!.
			</div>
			<span class="my-1 dark:text-orange-500">⌁</span>

			<div class="mb-2 text-center">
				<span class="text-sm text-slate-500 dark:text-zinc-500">Current Stack</span>

				<div class=" text-sm text-slate-700 dark:text-orange-500">
					Sveltekit • Tailwind4 • Cloudflare
				</div>
				<div class=" text-sm text-slate-700 dark:text-zinc-300">
					Prevoius: NextJS • Shadcn • StoryBook
				</div>
			</div>

			<span class="my-1 dark:text-orange-500">⌁</span>

			<div class="flex flex-col">
				<div class="text-center text-sm text-slate-500 dark:text-zinc-500">
					<span class="font-mono text-xs">2027</span> Projects
				</div>
				<div class="flex gap-4">
					<div>
						<a
							class="inline-flex w-full items-center justify-center text-center text-sm text-orange-600 dark:text-orange-500"
							href="/stackstore"
						>
							StackStore
						</a>
					</div>
					<div>
						<a
							class="inline-flex w-full items-center justify-center text-center text-sm text-orange-600 dark:text-orange-500"
							href="/metaful"
						>
							Metaful
						</a>
					</div>

					<div>
						<a
							class="inline-flex w-full items-center justify-center text-center text-sm text-orange-600 dark:text-orange-500"
							href="/kaleora"
						>
							Kaleora
						</a>
					</div>
					<div>
						<a
							class="inline-flex w-full items-center justify-center text-center text-sm text-orange-600 dark:text-orange-500"
							href="/obrand"
						>
							Obrand
						</a>
					</div>

					<div>
						<a
							class="inline-flex w-full items-center justify-center text-center text-sm text-orange-600 dark:text-orange-500"
							href="/eyecandy"
						>
							EyeCandy
						</a>
					</div>
				</div>
			</div>
		</div>
	{/if}
</div>
