<script lang="ts">
	function toggleDark() {
		const isDark = document.documentElement.classList.toggle('dark');
		localStorage.setItem('theme', isDark ? 'dark' : 'light');
	}
</script>

<div class=" bg-white text-zinc-900 dark:bg-zinc-950 dark:text-zinc-100">
	<button
		type="button"
		onclick={toggleDark}
		class="rounded-lg border border-zinc-200 bg-zinc-50 px-3 py-1.5 text-sm hover:bg-zinc-100 dark:border-zinc-800 dark:bg-zinc-900 dark:hover:bg-zinc-800"
	>
		Switch Theme
	</button>
</div>
