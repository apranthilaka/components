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
		class="flex h-12 w-full shrink-0 flex-row items-center justify-between border-b border-b-neutral-200 bg-slate-100 px-11 text-sm dark:border-b-zinc-900 dark:bg-zinc-950 dark:text-neutral-500"
	>
		<div>
			<a class="font-normal text-neutral-700 dark:text-zinc-200" href="./">@apranthilaka</a>
		</div>
		<Toggler />
	</header>

	<main class="no-scrollbar min-h-0 w-full max-w-360 flex-1 overflow-x-hidden overflow-y-auto">
		{@render children()}
	</main>
</div>
