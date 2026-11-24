<script>
	import { fly } from 'svelte/transition';
	import PurchaseCard from './components/PurchaseCard.svelte';

	let animationState = $state(false);

	$effect(() => {
		animationState = true;
	});

	let productCardDetails = $state([
		{
			imageUrl:
				'https://images.unsplash.com/photo-1718382341267-aef8a9e4ecef?q=80&w=2612&auto=format&fit=crop&ixlib=rb-4.1.0&ixid=NHwxMjA3fDA%3D',
			productType: 'Over-ear wireless headphones',
			productTitle: 'Apple AirPods Max',
			productDescription:
				'Premium over-ear headphones with active noise cancellation, Transparency mode, and Spatial Audio. ',
			productPrice: '$549.00'
		},
		{
			imageUrl:
				'https://plus.unsplash.com/premium_photo-1682148393028-d43b5782c9fc?q=80&w=2670&auto=format&fit=crop&ixlib=rb-4.1.0&ixid=NHwxMjA3fDA%3D',
			productType: 'Electronics · Smartphone',
			productTitle: 'Google Pixel 9',
			productDescription:
				'A feature-rich smartphone with an advanced camera system, bright display, and all-day battery life.',
			productPrice: '$799.00'
		},

		{
			imageUrl:
				'https://images.unsplash.com/photo-1600185365483-26d7a4cc7519?q=80&w=2650&auto=format&fit=crop&ixlib=rb-4.1.0&ixid=NHwxMjA3fDA%3D',
			productType: 'Running shoes',
			productTitle: 'Nike Air Zoom Pegasus',
			productDescription:
				'Lightweight running shoes with responsive cushioning and a breathable mesh, ideal for everyday use.',
			productPrice: '$130.00'
		}
	]);
</script>

{#if animationState}
	<main
		in:fly={{ y: 50, duration: 700 }}
		class="flex h-auto w-full max-w-360 flex-col gap-20 p-10 text-base text-slate-800 dark:text-zinc-300"
	>
		<div class="w-full">
			<p class="text-5xl font-semibold text-slate-950 dark:text-zinc-100">Stack Store UX Revamp</p>
			<p class="mt-4 text-3xl leading-11">
				As part of a recent UX initiative, I collaborated with a local e-commerce platform to audit
				the existing experience and solve critical usability bottlenecks. This case study highlights
				key friction points discovered during the audit and details the targeted design solutions
				implemented to optimize the overall user journey.
			</p>
		</div>
		<div class="w-full">
			<p class="text-xl font-semibold">Reducing Card Clutter & Simplifying Entry Points</p>
			<p class="text-lg">
				To reduce cognitive overload, product cards dynamically adapt to each step of the user
				flow—displaying only the essential information and actions required for that specific stage.
			</p>
		</div>

		<div class="flex w-full flex-col gap-5">
			<div
				class="grid auto-rows-150 grid-cols-[repeat(auto-fit,minmax(400px,1fr))] gap-5 rounded-lg border border-slate-300 bg-white px-8 py-9 dark:border-zinc-700 dark:bg-zinc-950"
			>
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

			<!-- <div
				class="grid auto-rows-150 grid-cols-[repeat(auto-fit,minmax(400px,1fr))] gap-5 rounded-lg border border-slate-300 bg-white px-8 py-9 dark:border-zinc-700 dark:bg-zinc-950"
			>
				<PurchaseCard />
			</div> -->
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
		in:fly|global={{ y: 50, duration: 500, delay: 100 + index * 150 }}
		class="flex h-full flex-col justify-center overflow-hidden rounded-lg border border-slate-200 bg-white shadow-sm dark:border-zinc-700 dark:bg-zinc-900"
	>
		<!-- image container  -->
		<div
			class="h-full w-full bg-cover bg-center bg-no-repeat"
			style:background-image="url('{imageUrl}')"
		></div>
		<!-- image container  -->

		<!-- data container  -->
		<div class="flex flex-col gap-3 px-8 py-7">
			<div class="font-mono text-xs text-slate-400 dark:text-zinc-400">{productType}</div>
			<div class="text-base font-semibold dark:text-zinc-100">{productTitle}</div>
			<div class="text-sm text-slate-600 dark:text-zinc-400">{productDescription}</div>
			<!-- <div>Selects</div> -->
			<div class="flex flex-row items-center justify-between">
				<div class="font-mono text-2xl font-bold dark:text-zinc-100">{productPrice}</div>

				<button
					class="flex h-11 items-center justify-center rounded-md border border-neutral-300 bg-neutral-100 px-5 text-sm text-[13px] font-semibold text-neutral-950 uppercase transition-all delay-75 hover:bg-neutral-950 hover:text-neutral-200 dark:border-zinc-700 dark:bg-zinc-900 dark:text-zinc-50 hover:dark:text-zinc-50"
				>
					Add to basket
				</button>
			</div>
		</div>
	</div>
{/snippet}
