<script lang="ts">
	// Components
	import CallToAction from "$lib/components/layout/CallToAction.svelte";

	// Icons
	import StakeholderGrid from "$lib/components/layout/StakeholderGrid.svelte";
	import Story from "./Story.svelte";
	import SecondaryHero from "$lib/components/layout/hero-sections/SecondaryHero.svelte";
	import Culture from "$lib/components/layout/Culture.svelte";

	// Constants
	const values = [
		{
			title: "Innovation",
			description: "Constantly challenging the status quo to create better solutions."
		},
		{
			title: "Integrity",
			description: "Building trust through transparent actions and honest communication."
		},
		{
			title: "Impact",
			description: "Measuring our success by the positive change we create for our clients."
		}
	];
</script>

<SecondaryHero
	title="AI for real estate and infrastructure"
	subtitle="Automates 75% of development work. Speeds up delivery by 80%."
	imageSrc="/mockups/airport-screen-1747857833694.png"
/>

<!-- Story Section -->
<Story
	paragraphs={[
		"Build was started by people who had done the work firsthand. From data centers to EV networks, the playbook never changed—ideas were clear, but timelines dragged. Teams spent months on desktop due diligence, buried in documents, maps, and municipal PDFs. There were modern tools for managing buildings—but none for developing them. As infrastructure scaled globally, the workflow stayed manual.",
		"We created Build to do what software hadn’t: remove the bottlenecks slowing the built world. Our AI agents handle over 75% of critical workflows in commercial infrastructure development. From filtering sites to generating permit drafts, each agent is built to speed up real work. The result? Timelines that used to take six weeks now take two days. Deliverables are 120% more profitable. And teams can expand scope—without expanding headcount.",
		"Today, Build powers new development across energy, logistics, storage, EV charging, and telecom. We’re trusted by enterprise teams deploying at global scale. Our platform is built to high security standards—compliant with SOC 2, GDPR, and CCPA—and proven in the field. Whether it's analyzing sites, acquiring utilities, or drafting zoning language, Build lets you go fast, stay accurate, and do more with less."
	]}
/>

<!-- Our Culture Section -->
<Culture {values} />

<!-- StakeholderGrid Section -->
<StakeholderGrid
	stakeholderType="team"
	title="Our team."
	subtitle="Led by experience."
	stakeholders={[
		{
			name: "James SE",
			position: "Founder",
			bio: "James SE is the founder of Build, leading the shift to AI-native workflows in commercial infrastructure development. He brings deep expertise in automating project delivery for energy, logistics, and telecom, enabling clients to scale faster and work smarter—globally and securely.",
			image: "/generated/image-a-professional-founder-headshot-capturin.webp"
		}
	]}
/>

<!-- No investors to display -->

<!-- CTA Section -->
<CallToAction
  title="The fastest way to build the physical world"
  subtitle="Join us or partner with Build"
  description="We’re opening up to just three more teams this quarter. Whether you’re building critical infrastructure or want to join Build to help us do it, we’d like to hear from you."
  callsToAction={[
    { href: '/careers', label: 'See open roles', variant: 'primary' },
    { href: '/contact', label: 'Partner with Build', variant: 'secondary' }
  ]}
/>
