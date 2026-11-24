<script>
	let { children } = $props();
</script>

<main class="flex h-auto w-full flex-col items-center p-11">
	{@render children()}
</main>
