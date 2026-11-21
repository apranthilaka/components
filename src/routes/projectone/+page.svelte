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
			productType: 'Over-ear wireless headphones',
			productTitle: 'Apple AirPods Max',
			productDescription:
				'Premium over-ear headphones with active noise cancellation, Transparency mode, and personalized Spatial Audio. The knit-mesh canopy and memory-foam ear cushions provide a comfortable fit for immersive listening.',
			productPrice: '$549.00'
		},
		{
			imageUrl:
				'https://images.unsplash.com/photo-1773070309549-8123488410d7?q=80&w=2400&auto=format&fit=crop&ixlib=rb-4.1.0&ixid=NHwxMjA3fDA%3D',
			productType: 'Skincare · Gel Facial Cleanser',
			productTitle: 'Éla de Pure Hydrating Cleanser',
			productDescription:
				'A gentle, sulfate-free gel cleanser for all skin types. Infused with aloe vera and hyaluronic acid to lift away impurities while leaving skin feeling soft and hydrated. 150 ml.',
			productPrice: '$549.99'
		},
		{
			imageUrl:
				'https://images.unsplash.com/photo-1600585154340-be6161a56a0c?q=80&w=2670&auto=format&fit=crop&ixlib=rb-4.1.0&ixid=NHwxMjA3fDA%3D',
			productType: 'House for sale',
			productTitle: 'Modern Family Home',
			productDescription:
				'3 bedrooms · 2 bathrooms · 1,850 sq ft. A bright modern home with an open-plan kitchen, landscaped garden, and attached garage.',
			productPrice: '$4M'
		},
		{
			imageUrl:
				'https://images.unsplash.com/photo-1503736334956-4c8f8e92946d?q=80&w=2564&auto=format&fit=crop&ixlib=rb-4.1.0&ixid=NHwxMjA3fDA%3D',
			productType: 'Sports car',
			productTitle: 'Porsche 911 Carrera',
			productDescription:
				'2024 · 2-door coupe · 3.0L twin-turbo. A precise, high-performance sports car with a rear-engine layout and premium leather interior.',
			productPrice: '$144,250'
		},
		{
			imageUrl:
				'https://images.unsplash.com/photo-1542291026-7eec264c27ff?q=80&w=2400&auto=format&fit=crop',
			productType: 'Running shoes',
			productTitle: 'Nike Air Zoom Pegasus',
			productDescription:
				'Lightweight road-running shoes with responsive cushioning and a breathable mesh upper, designed for everyday training.',
			productPrice: '$130.00'
		},
		{
			imageUrl:
				'https://images.unsplash.com/photo-1511707171634-5f897ff02aa9?q=80&w=2400&auto=format&fit=crop',
			productType: 'Electronics · Smartphone',
			productTitle: 'Google Pixel 9',
			productDescription:
				'A feature-rich smartphone with an advanced camera system, bright display, and all-day battery life.',
			productPrice: '$799.00'
		},
		{
			imageUrl:
				'https://images.unsplash.com/photo-1548036328-c9fa89d128fa?q=80&w=2400&auto=format&fit=crop',
			productType: 'Accessories · Leather handbag',
			productTitle: 'Everyday Leather Tote',
			productDescription:
				'A versatile carryall crafted from supple leather, with a roomy interior and secure zip pocket for daily essentials.',
			productPrice: '$185.00'
		},
		{
			imageUrl:
				'https://images.unsplash.com/photo-1505693416388-ac5ce068fe85?q=80&w=2400&auto=format&fit=crop',
			productType: 'Furniture · Lounge chair',
			productTitle: 'Harbor Accent Chair',
			productDescription:
				'A modern upholstered lounge chair with a supportive seat and warm wood legs, made for relaxed reading and quiet evenings.',
			productPrice: '$429.00'
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
			<div class="grid grid-cols-[repeat(auto-fit,minmax(500px,1fr))] gap-5">
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
		class="flex h-200 flex-col justify-center rounded-lg border border-slate-200 bg-white shadow-sm dark:border-zinc-700 dark:bg-zinc-900"
	>
		<div
			class="h-full w-full bg-cover bg-center bg-no-repeat"
			style:background-image="url('{imageUrl}')"
		></div>
		<!-- data container  -->
		<div class="flex flex-col gap-4 p-8">
			<div class="text-sm text-slate-400 dark:text-zinc-400">{productType}</div>
			<div class="text-3xl font-semibold dark:text-zinc-100">{productTitle}</div>
			<div class="text-slate-600 dark:text-zinc-400">{productDescription}</div>
			<div>Selects</div>
			<div class="flex flex-row items-center justify-between">
				<div class="font-mono text-3xl font-bold dark:text-zinc-100">{productPrice}</div>
				<div>
					<button
						class="h-12 rounded-md border bg-neutral-800 px-7 text-sm font-semibold text-slate-50 uppercase dark:border-zinc-700 dark:text-zinc-200 hover:dark:text-zinc-50"
						>Add to marsket</button
					>
				</div>
			</div>
		</div>
	</div>
{/snippet}
