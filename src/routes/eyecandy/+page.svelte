<script>
	import TitleSection from '#lib/components/TitleSection.svelte';
	import ComponentOne from './components/ComponentOne.svelte';
	let title = 'Metaful: Beautiful Components';
	let paragraph =
		'I love designing and experimenting with app components. After years of bringing ideas to life in Figma, I moved to code to explore polished interactions, responsive layouts, and real-world behavior—then test the results here.';
</script>

<div class="flex h-auto w-full flex-col gap-20 text-slate-800 dark:text-zinc-300">
	<TitleSection {title} {paragraph} />
	<div class="grid auto-rows-200 grid-cols-[repeat(auto-fit,minmax(700px,1fr))] gap-5">
		<div class="h-full w-full">
			<ComponentOne />
		</div>
		<div class="flex h-full w-full items-center justify-center border border-line">
			Work In Progress
		</div>
		<div class="flex h-full w-full items-center justify-center border">Work In Progress</div>
		<div class="flex h-full w-full items-center justify-center border">Work In Progress</div>
		<div class="flex h-full w-full items-center justify-center border">Work In Progress</div>
		<div class="flex h-full w-full items-center justify-center border">Work In Progress</div>
		<div class="flex h-full w-full items-center justify-center border">Work In Progress</div>
		<div class="flex h-full w-full items-center justify-center border">Work In Progress</div>
		<div class="flex h-full w-full items-center justify-center border">Work In Progress</div>
	</div>
</div>
