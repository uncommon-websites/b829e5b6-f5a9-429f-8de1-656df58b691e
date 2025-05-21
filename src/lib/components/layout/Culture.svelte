<script lang="ts">
	import SectionHeader from "$lib/components/layout/SectionHeader.svelte";
	import { animate, stagger } from "motion";
	import { onMount } from "svelte";

	// Types
	export type Value = {
		title: string;
		description: string;
	};

	// Props
	const { values = [
  {
    title: "Hands-on, not hands-off",
    description: "We're engineers, operators, and infrastructure experts who work side-by-side with the world’s largest developers and agencies. From zoning setbacks to fiber layer maps, we find out what really slows things down—and then we fix it."
  },
  {
    title: "Low ego. High speed.",
    description: "The best teams work without politics or posturing. Our culture is built on honest input, tight collaboration, and a bias for execution—whether it’s code commits or site feasibility reviews."
  },
  {
    title: "Impact beyond headcount",
    description: "Build’s AI-native platform does what infrastructure teams love but can’t scale: thoughtful analysis, precise workflows, and scenario planning. We help builders take on GDP-scale work—without the burnout."
  },
  {
    title: "Real stuff. First principles. No fluff.",
    description: "If you want to work on frontier software and deliver impact in hours and weeks, not quarters, you’ll fit right in. Our tools power workstreams for real assets: energy, logistics, broadband access, and more."
  }
]: { values: Value[] } = $props();

	let cards: HTMLElement[] = $state([]);

	onMount(() => {
		if (!cards.length) return;
		animate(
			cards,
			{
				y: ["1.5rem", 0],
				filter: ["blur(2px)", "blur(0px)"],
				opacity: [0, 1]
			},
			{
				duration: 0.3,
				ease: "easeOut",
				delay: stagger(0.1, {
					ease: "easeInOut"
				})
			}
		);
	});
</script>

<section class="bg-white dark:bg-gray-950">
	<div
		class="section-py section-px container mx-auto grid gap-8 [--gap:--spacing(8)] [--radius:var(--radius-2xl)]"
	>
		<SectionHeader title="The platform is powerful. The people are the reason." subtitle="Culture and values at Build" />

		<div
			class="grid gap-(--gap)"
			style:grid-template-columns="repeat(auto-fit, minmax(280px, 1fr))"
		>
			{#each values as value, i}
				<div
					bind:this={cards[i]}
					class="relative border-t border-gray-200 pt-4 dark:border-gray-900"
				>
					<!-- Content -->
					<div class="text-caption z-10">
						<div>
							<div class="text-headline mb-[1em]">{value.title}</div>
							<div class="text-body text-gray-500 dark:text-gray-400">{value.description}</div>
						</div>
					</div>
				</div>
			{/each}
		</div>
	</div>
</section>
