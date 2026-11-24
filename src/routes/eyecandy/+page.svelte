<script>
	import ComponentOne from './components/ComponentOne.svelte';
</script>

<div class="flex flex-col gap-20 text-base text-slate-800 dark:text-zinc-300">
	<div class="max-w-300">
		<p class="text-5xl font-semibold text-slate-950 dark:text-zinc-100">
			Metaful: Beautiful Components
		</p>
		<p class="mt-4 text-3xl leading-11">
			I love designing and experimenting with app components. After years of bringing ideas to life
			in Figma, I moved to code to explore polished interactions, responsive layouts, and real-world
			behavior—then test the results here.
		</p>
	</div>
	<div class="grid auto-rows-200 grid-cols-[repeat(auto-fit,minmax(700px,1fr))]">
		<div class="h-full w-full border">
			<ComponentOne />
		</div>
		<div class="h-full w-full border">Data 1</div>
		<div class="h-full w-full border">Data 1</div>
		<div class="h-full w-full border">Data 1</div>
		<div class="h-full w-full border">Data 1</div>
		<div class="h-full w-full border">Data 1</div>
		<div class="h-full w-full border">Data 1</div>
		<div class="h-full w-full border">Data 1</div>
	</div>
</div>
