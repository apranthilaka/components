<script lang="ts">
	import { Sun, Moon } from '@lucide/svelte';

	function toggleDark() {
		const isDark = document.documentElement.classList.toggle('dark');
		localStorage.setItem('theme', isDark ? 'dark' : 'light');
	}
</script>

<div class=" bg-white text-zinc-900 dark:bg-zinc-950 dark:text-zinc-100">
	<button
		type="button"
		onclick={toggleDark}
		class="inline-flex h-9 w-9 items-center justify-center gap-2 rounded-lg border border-zinc-200 bg-zinc-50 text-sm hover:bg-zinc-100 dark:border-zinc-800 dark:bg-zinc-900 dark:hover:bg-zinc-800"
	>
		<Moon size={16} class="block dark:hidden" />
		<Sun size={16} class="hidden dark:block" />
	</button>
</div>
