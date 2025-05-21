<script lang="ts">
	// Types

	// Components
	import SectionHeader from "$lib/components/layout/SectionHeader.svelte";
	import Culture from "$lib/components/layout/Culture.svelte";
	import Testimonials from "$lib/components/layout/Testimonials.svelte";
	import SecondaryHero from "$lib/components/layout/hero-sections/SecondaryHero.svelte";
	import Card from "$lib/components/ui/Card.svelte";
	import JobList, { type JobOpening } from "./JobList.svelte";

	// Icons
	import IconBriefcase from "~icons/lucide/briefcase";
	import IconUsers from "~icons/lucide/users";
	import IconHeart from "~icons/lucide/heart";
	import IconGlobe from "~icons/lucide/globe";

	// Constants
	const SECTION_BASE_CLASSES = "section-py section-px container mx-auto";
	const GRADIENT_BG_CLASSES =
		"bg-gradient-to-br from-gray-50 to-gray-100 dark:from-gray-900 dark:to-gray-800";
	const ICON_CONTAINER_CLASSES =
		"bg-primary-50 text-primary-600 dark:bg-primary-950 dark:text-primary-400 flex items-center justify-center rounded-full";

	const benefits = [
  {
    title: "Real-world impact",
    description: "Your work powers data centers, energy projects, and digital infrastructure—changing what gets built and how fast it happens.",
    icon: IconGlobe
  },
  {
    title: "Ownership at scale",
    description: "Join a small team where you own projects end-to-end and work directly with founders, customers, and industry leaders.",
    icon: IconBriefcase
  },
  {
    title: "Elite growth & autonomy",
    description: "Steep growth curves, real responsibility from day one, and the flexibility to shape your role as we grow.",
    icon: IconUsers
  },
  {
    title: "Forward deployed opportunities",
    description: "Get hands-on with customer projects or join forward deployed engineering squads when needed—no ivory towers here.",
    icon: IconHeart
  }
];

	const openings: JobOpening[] = [
		// Engineering
		{
			title: "Senior Frontend Developer",
			department: "Engineering",
			location: "Remote",
			type: "Full-time",
			url: "#"
		},
		{
			title: "Backend Engineer",
			department: "Engineering",
			location: "Remote",
			type: "Full-time",
			url: "#"
		},
		{
			title: "Design Engineer",
			department: "Engineering",
			location: "Remote",
			type: "Full-time",
			url: "#"
		},

		// Design
		{
			title: "UX/UI Designer",
			department: "Design",
			location: "Remote",
			type: "Full-time",
			url: "#"
		},
		{
			title: "Product Designer",
			department: "Design",
			location: "Remote",
			type: "Full-time",
			url: "#"
		},

		// Product
		{
			title: "Product Manager",
			department: "Product",
			location: "Remote",
			type: "Full-time",
			url: "#"
		},
		{
			title: "Product Analyst",
			department: "Product",
			location: "Remote",
			type: "Full-time",
			url: "#"
		},

		// Marketing
		{
			title: "Marketing Specialist",
			department: "Marketing",
			location: "Remote",
			type: "Full-time",
			url: "#"
		},
		{
			title: "Content Strategist",
			department: "Marketing",
			location: "Remote",
			type: "Full-time",
			url: "#"
		},
		{
			title: "Social Media Manager",
			department: "Marketing",
			location: "Remote",
			type: "Full-time",
			url: "#"
		}
	];

	const employeeTestimonials = [
  {
    name: "Zari Kinsey",
    position: "Operations Strategist",
    company: "Productivity Systems Team",
    quote:
      "Joining Build felt like finding a team that actually values curiosity and collaboration. In ops, things move quick—but the support is real. My manager took time to map out my growth plan in month one, and I’ve since led cross-functional work I never imagined I’d do this early in my career.",
    image:
      "/generated/image-a-black-woman-smiling-in-a-casual-office.webp"
  },
  {
    name: "Om Tejani",
    position: "Software Engineer",
    company: "Intelligent Agent Team",
    quote:
      "As a junior engineer, I assumed I’d just fix bugs for a while—but I shipped features within my second week. The mentorship here is incredible. Senior engineers actually sit with you and pair on challenging design problems, and you’re not just implementing—you’re thinking end-to-end.",
    image:
      "/generated/image-a-south-asian-man-working-in-an-open-mod.webp"
  },
  {
    name: "Rowan Burke",
    position: "Director of Product",
    company: "Infrastructure Tooling",
    quote:
      "Build isn’t just solving a hard problem—they’re respectful of how different people solve it. Leadership here thrives on individual ownership, not micromanagement. I’ve been able to push our roadmap forward with full trust, and collaborate across engineering, AI, and clients—all without layers of red tape.",
    image:
      "/generated/image-a-white-woman-leading-a-meeting-in-a-mod.webp"
  }
];

	const processSteps = [
  {
    step: 1,
    title: "Apply online",
    description: "Send us a quick intro and your resume or LinkedIn. No cover letter required, and we review every application within 7 days."
  },
  {
    step: 2,
    title: "Meet the team",
    description: "Join a 30-minute call with your hiring manager and one of the founders—no formalities, just a straightforward conversation."
  },
  {
    step: 3,
    title: "Short trial project",
    description: "Complete a brief paid exercise based on actual work you’ll do here. We respect your time and pay for your effort."
  },
  {
    step: 4,
    title: "Decision fast",
    description: "We avoid drawn-out interview loops. Once we align, you’ll get a call and an offer within days."
  }
];

	const values = [
  {
    icon: IconGlobe,
    title: "Bias for action",
    description: "We move fast and bias toward shipping impactful work, not endless iteration or consensus for consensus’ sake."
  },
  {
    icon: IconBriefcase,
    title: "Extreme ownership",
    description: "Everyone operates like an owner—full responsibility, real trust, and cross-functional scope from day one."
  },
  {
    icon: IconUsers,
    title: "Direct communication",
    description: "We are candid and respectful—clear feedback, few meetings, and async by default to maximize deep work."
  },
  {
    icon: IconHeart,
    title: "Customer obsession",
    description: "We solve the hardest problems that matter most to our users—building for real-world results, not just PR."
  }
];
</script>

<!-- Hero Section -->

<SecondaryHero
	title="Build the future of infrastructure"
	subtitle="Work with an AI-native team accelerating real-world impact"
	imageSrc="/generated/image-a-modern-office-environment-with-a-diver.webp"
/>

<!-- Why Join Us Section -->
<section class={SECTION_BASE_CLASSES}>
	<SectionHeader title="Why join us?" subtitle="Build your career while making an impact" />

	<div class="mt-16 grid gap-4 md:grid-cols-3">
		{#each benefits as benefit}
			<Card {...benefit} />
		{/each}
	</div>
</section>

<!-- Culture Section -->
<Culture {values} />

<Testimonials testimonials={employeeTestimonials} />

<!-- Application Process -->
<section class={SECTION_BASE_CLASSES}>
	<div class="mx-auto">
		<h2 class="text-title1 mb-16">Our application process</h2>

		<div class="grid gap-12 md:grid-cols-3">
			{#each processSteps as { step, title, description }, i}
				<div class="flex flex-col">
					<div class="{ICON_CONTAINER_CLASSES} mb-6 size-11">
						<span class="text-headline">{step}</span>
					</div>
					<h3 class="text-headline mb-3">{title}</h3>
					<p class="text-body text-emphasis-low">{description}</p>
				</div>
			{/each}
		</div>
	</div>
</section>
<!-- Current Openings Section -->
<section class={GRADIENT_BG_CLASSES}>
	<div class="section-px section-py container mx-auto grid w-full items-start lg:grid-cols-2">
		<SectionHeader title="Current openings" subtitle="Find your perfect role" />

		<JobList {openings} />
	</div>
</section>
