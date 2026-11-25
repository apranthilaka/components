<script lang="ts">
	import './layout.css';
	import favicon from '#lib/assets/favicon.svg';
	import type { LayoutProps } from './$types';
	import Toggler from '#lib/components/Toggler.svelte';

	let { children }: LayoutProps = $props();
</script>

<svelte:head>
	<link rel="icon" href={favicon} />
</svelte:head>

<div class="flex h-screen w-full flex-col items-center justify-center overflow-hidden">
	<header
		class="flex h-15 w-full shrink-0 flex-row items-center justify-between border-b border-b-neutral-200 bg-neutral-100 px-11 text-sm dark:border-b-zinc-900 dark:bg-neutral-950 dark:text-neutral-500"
	>
		<div class="flex flex-row gap-4">
			<a class=" font-jetbrains text-sm text-neutral-700 dark:text-orange-500" href="./">
				@components
			</a>
		</div>
		<div class="flex flex-row items-center gap-4">
			<a
				target="_blank"
				class=" font-jetbrains text-sm text-neutral-700 dark:text-orange-500"
				href="https://apranthilaka.com/"
			>
				@apranthilaka
			</a>
			<a
				target="_blank"
				class=" cursor-not-allowed font-jetbrains text-sm text-neutral-700 dark:text-orange-500"
				href="#"
			>
				About Me
			</a>
			<Toggler />
		</div>
	</header>

	<main
		class="no-scrollbar flex min-h-0 w-full flex-1 flex-col items-center overflow-x-hidden overflow-y-auto"
	>
		{@render children()}
	</main>
</div>
