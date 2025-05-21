<script lang="ts">
	// Types
	import type { PageProps } from "./$types";

	// Components
	import Features from "$lib/components/layout/Features.svelte";
	import Testimonials from "$lib/components/layout/Testimonials.svelte";
	import CallToAction from "$lib/components/layout/CallToAction.svelte";
	import Pricing from "$lib/components/layout/Pricing.svelte";

	// Props
	const { data }: PageProps = $props();
</script>

<Pricing />

<Testimonials
	testimonials={[
  {
    name: "Ricardo Zheng",
    position: "Managing Director",
    company: "Blueform Development",
    quote:
      "We cut weeks from diligence timelines and delivered more projects with the same team size. It's no exaggeration—Build changed how our office works.",
    image: "/generated/image-a-middle-aged-chinese-man-in-a-professio.webp"
  },
  {
    name: "Elspeth Dahan",
    position: "VP of Project Execution",
    company: "Verdant Infrastructure",
    quote:
      "Our first project with Build delivered in half the time. And our margins on the package went up 2x. Nothing else on the market comes close.",
    image: "/generated/image-a-black-british-woman-in-a-professional-.webp"
  },
  {
    name: "Malik Rausch",
    position: "Director of Growth",
    company: "StrataNet Solutions",
    quote:
      "Every developer I know is asking the same question—how do we do more without hiring 30 analysts? Build is the only serious answer I’ve seen.",
    image: "/generated/image-a-young-south-asian-man-in-a-professiona.webp"
  }
]}
/>

<CallToAction
	title="Move faster than red tape"
	subtitle="Build automates infrastructure development—so you can scale operations, not headcount"
	description="Build’s AI-native platform cuts weeks of manual work down to hours. Automate site selection, due diligence, permitting, utility acquisition, and more—across energy, digital infrastructure, logistics, and telecom. 75% of tasks, off your team’s plate. Our AI agents don’t just summarize. They search, decide, and act—executing the workflows mezzanine and field teams run every day, across land, legal, and local regulators. Build reduces due diligence time by 80%, enabling you to unlock new opportunities faster and keep internal teams focused where it counts."
	imageSrc="/generated/image-a-cheerful-real-estate-professional-in-a.webp"
	callsToAction={[
		{ href: '/contact', label: 'Request access', variant: 'primary' }
	]}
/>
