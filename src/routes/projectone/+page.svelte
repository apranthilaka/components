<script>
	import { resolve } from '$app/paths';
	import { fly } from 'svelte/transition';

	let animationState = $state(false);

	$effect(() => {
		animationState = true;
	});

	let productCardDetails = $state([
		{
			imageUrl:
				'https://images.unsplash.com/photo-1600375104627-c94c416deefa?q=80&w=2680&auto=format&fit=crop&ixlib=rb-4.1.0&ixid=NHwxMjA3fDA%3D',
			productType: 'Electronics and Audio',
			productTitle: 'AirPods Max',
			productDescription:
				'A perfect balance of exhilarating high-quality audio and the effortless magic of AirPods.',
			productPrice: '$25.25'
		},
		{
			imageUrl:
				'https://images.unsplash.com/photo-1773070309549-8123488410d7?q=80&w=2400&auto=format&fit=crop&ixlib=rb-4.1.0&ixid=NHwxMjA3fDA%3D',
			productType: 'Gel Facial Cleanser',
			productTitle: 'Ela De Pure',
			productDescription:
				"A gentle daily cleanser infused with nourishing botanical extracts to purify, hydrate, and restore your skin's natural glow.",
			productPrice: '$549.99'
		},
		{
			imageUrl:
				'https://images.unsplash.com/photo-1434082033009-b81d41d32e1c?q=80&w=2670&auto=format&fit=crop&ixlib=rb-4.1.0&ixid=NHwxMjA3fDA%3D',
			productType: 'shampoo',
			productTitle: 'shampoo boottl 4',
			productDescription: 'sdgfsfd sdfsfd sdfsfd sdfsf  sdfsf ',
			productPrice: '$125.25'
		},
		{
			imageUrl:
				'https://images.unsplash.com/photo-1605559424843-9e4c228bf1c2?q=80&w=2564&auto=format&fit=crop&ixlib=rb-4.1.0&ixid=NHwxMjA3fDA%3D',
			productType: 'shampoo',
			productTitle: 'shampoo boottl 3',
			productDescription: 'sdgfsfd sdfsfd sdfsfd sdfsf  sdfsf ',
			productPrice: '$125.25'
		}
	]);
</script>

{#if animationState}
	<main
		in:fly={{ y: 20, duration: 700 }}
		class="flex flex-col gap-20 p-11 text-base text-slate-800 dark:text-zinc-300"
	>
		<div>
			<p class="text-5xl font-semibold text-slate-950 dark:text-zinc-100">Stack Store UX Revamp</p>
			<p class="mt-4 text-3xl leading-11">
				As part of a recent UX initiative, I collaborated with a local e-commerce platform to audit
				the existing experience and solve critical usability bottlenecks. This case study highlights
				key friction points discovered during the audit and details the targeted design solutions
				implemented to optimize the overall user journey.
			</p>
		</div>
		<div>
			<p class="text-xl font-semibold">Reducing Card Clutter & Simplifying Entry Points</p>
			<p class="text-lg">
				To reduce cognitive overload, product cards dynamically adapt to each step of the user
				flow—displaying only the essential information and actions required for that specific stage.
			</p>
		</div>

		<div>
			<div class="grid grid-cols-[repeat(auto-fit,minmax(500px,1fr))] gap-12">
				{#each productCardDetails as cardDetails, index (cardDetails.productTitle)}
					{@render simpleProductCard({
						imageUrl: cardDetails.imageUrl,
						productType: cardDetails.productType,
						productTitle: cardDetails.productTitle,
						productDescription: cardDetails.productDescription,
						productPrice: cardDetails.productPrice,
						index
					})}
				{/each}
			</div>
		</div>
	</main>
{/if}

{#snippet simpleProductCard({
	imageUrl,
	productType,
	productTitle,
	productDescription,
	productPrice,
	index = 0
})}
	<div
		in:fly={{ y: 200, duration: 500, delay: 100 + index * 5000 }}
		class="flex h-200 flex-col justify-center rounded-lg border dark:border-zinc-700 dark:bg-zinc-900"
	>
		<div
			class="h-full w-full bg-cover bg-center bg-no-repeat"
			style:background-image="url('{imageUrl}')"
		></div>
		<!-- data container  -->
		<div class="flex flex-col gap-3 p-6">
			<div class="text-sm dark:text-zinc-400">{productType}</div>
			<div class="text-3xl font-semibold dark:text-zinc-100">{productTitle}</div>
			<div class="dark:text-zinc-400">{productDescription}</div>
			<div>Selects</div>
			<div class="flex flex-row items-center justify-between">
				<div class="font-mono text-3xl font-bold dark:text-zinc-100">{productPrice}</div>
				<div>
					<button
						class="h-12 rounded-lg border px-7 text-sm font-semibold uppercase dark:border-zinc-700 dark:text-zinc-200 hover:dark:text-zinc-50"
						>Add to marsket</button
					>
				</div>
			</div>
		</div>
	</div>
{/snippet}
