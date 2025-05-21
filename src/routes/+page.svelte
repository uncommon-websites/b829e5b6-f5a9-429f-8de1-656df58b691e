<script lang="ts">
	// Components
	import UseCases from "$lib/components/layout/UseCases.svelte";
	import Summary from "$lib/components/layout/Summary.svelte";
	import Features from "$lib/components/layout/Features.svelte";
	import Testimonials from "$lib/components/layout/Testimonials.svelte";
	import CallToAction from "$lib/components/layout/CallToAction.svelte";
	import AboutTeaser from "$lib/components/layout/AboutTeaser.svelte";
	import LogoScroller from "$lib/components/layout/LogoScroller.svelte";
	import CustomerCardHero from "$lib/components/layout/hero-sections/CustomerCardHero.svelte";
</script>

<CustomerCardHero
  centered={false}
  title="Deliver infrastructure, without the drag"
  subtitle="Rebuild how you develop energy systems, data centers, and telecom—accelerate timelines, simplify workflows, and increase margin without adding headcount."
  customers={[
    {
      name: "Linda Park",
      position: "CRE Investor",
      imageSrc: "/generated/image-a-real-estate-investor-wearing-a-suit-st.webp"
    },
    {
      name: "Rachel Thomas",
      position: "Technology Executive",
      imageSrc: "/generated/image-a-female-executive-in-a-spacious-office-.webp"
    },
    {
      name: "Derrick Carter",
      position: "Infrastructure Manager",
      imageSrc: "/generated/image-an-african-american-manager-stands-confi.webp"
    },
    {
      name: "Michelle Cortez",
      position: "Government Affairs",
      imageSrc: "/generated/image-a-female-government-official-dons-a-hard.webp"
    },
    {
      name: "Walter Green",
      position: "Logistics Director",
      imageSrc: "/generated/image-a-senior-logistics-director-dressed-in-f.webp"
    }
  ]}
/>
<LogoScroller 
	label="Trusted by industry leaders"
	logoUrls={[
		'https://logo.clearbit.com/cbre.com',
		'https://logo.clearbit.com/jll.com',
		'https://logo.clearbit.com/duke-energy.com',
		'https://logo.clearbit.com/prologis.com'
	]}
/>

<Summary
	title="AI automation for infrastructure deployment"
	text="Build accelerates deployment of critical infrastructure with AI-native automation. Our platform automates 75% of development workflows so you can cut timelines from weeks to hours and scale without adding headcount."
/>

<Testimonials
	testimonials={[
		{
			name: "Elena Vaughn",
			position: "VP of Development",
			company: "GridPoint Renewables",
			quote:
				"We were staring down a 6-week due diligence sprint. Build did it in 2 days—and more exhaustively than we've ever seen.",
			image: "/generated/image-a-female-executive-in-the-renewable-ener.webp"
		},
		{
			name: "Caleb Minn",
			position: "Head of Strategy",
			company: "UltraSite Logistics",
			quote:
				"We’ve pulled 5 full-time workflows out of BusDev and handed them to agents. Everything moves faster now.",
			image: "/generated/image-a-north-american-male-logistics-leader-s.webp"
		},
		{
			name: "Renato Kim",
			position: "VP of Deployment",
			company: "VoltEdge Infrastructure",
			quote:
				"Build showed us where our teams were consistently wasting time. We haven’t hired since—and we’ve built more.",
			image: "/generated/image-a-korean-male-executive-in-a-tailored-su.webp"
		}
	]}
/>

<Features
	title="Built for modern infrastructure teams"
	subtitle="Powerful AI-native tools tailored for data centers, energy, and logistics."
	features={[
		{
			title: "Automate diligence in hours",
			description:
				"Generate full site reports and analysis in 48 hours, not 6 weeks—agents handle data collection, evaluation, and reporting."
		},
		{
			title: "Accelerate permitting and approvals",
			description:
				"Get applications and documents drafted by agents, reviewed by experts, and submitted in hours instead of weeks."
		},
		{
			title: "Boost margins on every project",
			description:
				"Increase core deliverable margins by over 120% without expanding your teams or adding headcount."
		},
		{
			title: "Multi-asset, multi-market workflows",
			description:
				"Support for data centers, energy, logistics, telecom, and more—all automated in one platform."
		},
		{
			title: "Enterprise-grade security",
			description:
				"SOC2, GDPR, and CCPA compliant from day one—trusted by leading infrastructure teams."
		},
		{
			title: "Forward-deployed engineering",
			description:
				"Our experts work on-site with your team to deliver automation and support, on your terms."
		}
	]}
/>

<UseCases
  title="Use Cases"
  subtitle="Real-world applications for your business needs"
  useCases={[
    {
      title: "Accelerate site assessment",
      description: "Instantly review and qualify sites with agent-powered due diligence—reducing timelines from weeks to days for data centers and infrastructure projects.",
      image: "/generated/image-a-project-manager-and-an-engineer-review.webp",
      link: {
        href: "/use-cases/accelerate-site-assessment",
        label: "Learn more"
      }
    },
    {
      title: "Simplify multi-asset deployment",
      description: "Coordinate energy, telecom, and logistics rollout in one platform. Align cross-functional teams, manage risk, and track progress in real time.",
      image: "/generated/image-a-diverse-team-of-telecom-and-energy-ope.webp",
      link: {
        href: "/use-cases/multi-asset-deployment",
        label: "Learn more"
      }
    },
    {
      title: "Modernize urban development",
      description: "Empower planners and developers to visualize scenarios, prepare documentation, and accelerate permitting with AI automation at every step.",
      image: "/generated/image-urban-planners-and-developers-discussing.webp",
      link: {
        href: "/use-cases/modernize-urban-development",
        label: "Learn more"
      }
    }
  ]}
/>

<AboutTeaser />
<CallToAction
  title="Accelerate infrastructure projects without scaling your team"
  subtitle="Cut timelines by 80% with AI agents purpose-built to automate real estate and infrastructure workflows."
  description="Build helps CRE, energy, and digital infrastructure teams eliminate bottlenecks, move faster on high-value sites, and deliver critical projects—from data centers to solar farms—at scale."
  imageSrc="/generated/image-a-cheerful-real-estate-developer-standin.webp"
  callsToAction={[
    {
      href: '/demo',
      label: 'Book a demo',
      variant: 'primary'
    },
    {
      href: '/contact',
      label: 'Talk to sales',
      variant: 'secondary'
    }
  ]}
/>
