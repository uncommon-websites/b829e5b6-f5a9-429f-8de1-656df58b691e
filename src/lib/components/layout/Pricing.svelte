<!--
@component Pricing

Please update features according to the company's product offering. Do not remove this comment.
-->
<script lang="ts">
	// Types
	type PricingTier = {
		name: string;
		monthlyPrice?: number | null;
		yearlyPrice?: number | null;
		description: string;
		features: string[];
		cta: {
			label: string;
			href: string;
		};
		highlight?: boolean;
	};

	type PricingFeature = {
		name: string;
		tiers: {
			[key: string]: boolean | string;
		};
	};

	// Components
	import Button from "$lib/components/ui/Button.svelte";
	import SectionHeader from "./SectionHeader.svelte";
	import IconCheck from "~icons/lucide/check";
	import IconX from "~icons/lucide/x";
	import NumberFlow from "@number-flow/svelte";
	import LogoScroller from "./LogoScroller.svelte";

	// Props
	const {
		title = "Simple, transparent pricing",
		subtitle = "Choose the plan that works best for your needs",
		tierNames = ["Starter", "Professional", "Enterprise"],
		features = [
		{
			name: "AI agent automation",
			tiers: {
				Starter: "Core workflows",
				Professional: "Advanced automations",
				Enterprise: "Fully custom"
			}
		},
		{
			name: "Due diligence accelerator",
			tiers: {
				Starter: "48 hour reports",
				Professional: "Multi-market, 48 hour reports",
				Enterprise: "Custom turnaround and asset types"
			}
		},
		{
			name: "Workflow automation",
			tiers: {
				Starter: "Site screening, zoning, docs",
				Professional: "Permitting, utility, test fits",
				Enterprise: "Custom build & expand as needed"
			}
		},
		{
			name: "Site selection tools",
			tiers: {
				Starter: true,
				Professional: true,
				Enterprise: true
			}
		},
		{
			name: "Integrations (public data)",
			tiers: {
				Starter: "Basic parcel/tax data",
				Professional: "Pipeline and GIS",
				Enterprise: "Custom integrations"
			}
		},
		{
			name: "Team collaboration",
			tiers: {
				Starter: false,
				Professional: true,
				Enterprise: true
			}
		},
		{
			name: "Compliance & security (SOC2, GDPR, CCPA)",
			tiers: {
				Starter: true,
				Professional: true,
				Enterprise: true
			}
		},
		{
			name: "API access",
			tiers: {
				Starter: false,
				Professional: true,
				Enterprise: "Enterprise/scalable endpoints"
			}
		},
		{
			name: "Agent customization",
			tiers: {
				Starter: false,
				Professional: "Limited",
				Enterprise: "Full custom agents"
			}
		},
		{
			name: "Document automation",
			tiers: {
				Starter: "Basic",
				Professional: "Advanced",
				Enterprise: "Custom templates"
			}
		},
		{
			name: "Support response time",
			tiers: {
				Starter: "By email, 48 hours",
				Professional: "Priority, 12 hours",
				Enterprise: "Premium, 4 hours + live agent"
			}
		},
		{
			name: "Onboarding",
			tiers: {
				Starter: "Self-serve & weekly office hours",
				Professional: "Guided onboarding",
				Enterprise: "Enterprise-level, on-site if needed"
			}
		},
		{
			name: "Forward-deployed Build engineering",
			tiers: {
				Starter: false,
				Professional: false,
				Enterprise: true
			}
		},
		{
			name: "Governance & SSO",
			tiers: {
				Starter: false,
				Professional: false,
				Enterprise: true
			}
		}
	],
		tiers = [
			{
				name: "Starter",
				monthlyPrice: null,
				yearlyPrice: null,
				description: "Best for smaller or emerging infrastructure developers ready to automate their first workflows.",
				features: [
					"Core AI agent workflows (site screening, zoning, due diligence)",
					"48-hour due diligence reports",
					"Basic integrations with public parcel and tax data",
					"Document automation (basic)",
					"Compliance & security: SOC2, GDPR, CCPA",
					"Self-serve onboarding and weekly office hours",
					"Email support (48hr response)"
				],
				cta: {
					label: "Book a demo",
					href: "/contact?plan=starter"
				}
			},
			{
				name: "Professional",
				monthlyPrice: null,
				yearlyPrice: null,
				description: "Designed for regional and national teams scaling automated CRE or infrastructure projects across multiple markets.",
				features: [
					"Everything in Starter",
					"Advanced agent automations (permitting, test fits, utility acquisition, document drafting)",
					"Multi-market workflow automation",
					"Pipeline & GIS data integrations",
					"Team collaboration tools",
					"API access",
					"Agent customization (limited)",
					"Document automation (advanced)",
					"Guided onboarding",
					"Priority support (12hr response)",
					"Dedicated implementation contact"
				],
				cta: {
					label: "Request a quote",
					href: "/contact?plan=professional"
				},
				highlight: true
			},
			{
				name: "Enterprise",
				monthlyPrice: null,
				yearlyPrice: null,
				description: "Comprehensive automation for hyperscale, public sector, or mission-critical organizations—fully customized and deployed to your requirements.",
				features: [
					"Everything in Professional",
					"Fully custom agent workflows",
					"Custom integrations (procurement, permitting, internal GIS, etc)",
					"Governance, user provisioning, SSO",
					"Forward-deployed Build engineering",
					"On-site onboarding available",
					"Premium support: 4hr and live agent escalation"
				],
				cta: {
					label: "Contact sales",
					href: "/contact?plan=enterprise"
				}
			}
		]
	}: {
		title?: string;
		subtitle?: string;
		tiers?: PricingTier[];
		features?: PricingFeature[];
		tierNames?: string[];
		caption?: string;
	} = $props();

	// State
	let annual = $state(true);
</script>

<section class="section-py section-px container mx-auto">
	<div class="flex flex-col items-baseline justify-between lg:flex-row">
		<SectionHeader {title} {subtitle} />

		<div class="mb-8 flex justify-center">
			<div class="inline-flex items-center rounded-full bg-gray-100 p-0.5 dark:bg-gray-800">
				<Button
					variant="ghost"
					size="sm"
					class=" {!annual ? 'bg-white shadow-sm dark:bg-gray-700' : ''}"
					onclick={() => (annual = false)}
				>
					Monthly
				</Button>
				<Button
					variant="ghost"
					size="sm"
					rounded
					class={annual ? "bg-white shadow-sm dark:bg-gray-700" : ""}
					onclick={() => (annual = true)}
				>
					Annual <span class="text-primary-600 dark:text-primary-400 text-footnote">Save 20%</span>
				</Button>
			</div>
		</div>
	</div>

	<div class="bb grid gap-6 md:grid-cols-2 lg:grid-cols-3">
		{#each tiers as tier}
			<div
				class="flex flex-col rounded-xl bg-white p-6 ring ring-gray-200 transition-all duration-300 dark:bg-gray-800 dark:ring-gray-700"
				class:ring-2={tier.highlight}
				class:ring-primary={tier.highlight}
				class:dark:ring-primary-700={tier.highlight}
				class:translate-y-[-4px]={tier.highlight}
			>
				<div class="mb-8">
					<h3 class="text-title3 mb-4 dark:text-white">{tier.name}</h3>
					<div class="mt-2 flex items-baseline">
						{#if tier.monthlyPrice === null && tier.yearlyPrice === null}
							<span class="text-title2 dark:text-white">Custom</span>
						{:else}
							<NumberFlow
								class="text-title2 [&::part\(suffix\)]:text-caption dark:text-white"
								format={{
									style: "currency",
									currency: "USD",
									trailingZeroDisplay: "stripIfInteger"
								}}
								value={annual ? tier.yearlyPrice : tier.monthlyPrice}
								suffix="/month"
							/>
						{/if}
					</div>
					<p class="text-callout text-emphasis-medium mt-3 dark:text-gray-300">
						{tier.description}
					</p>
				</div>

				<div class="mb-8 flex-grow">
					<ul class="space-y-3">
						{#each tier.features as feature}
							<li class="flex items-center gap-2">
								<IconCheck class="text-primary-600 dark:text-primary-400 size-5 flex-shrink-0" />
								<span class="text-body text-emphasis-medium dark:text-gray-300">{feature}</span>
							</li>
						{/each}
					</ul>
				</div>

				<div class="mt-auto">
					<Button
						href={tier.cta.href}
						variant={tier.highlight ? "primary" : "secondary"}
						class="w-full"
					>
						{tier.cta.label}
					</Button>
				</div>
			</div>
		{/each}
	</div>
	<div class="mt-32">
		<!-- Responsive table wrapper with horizontal scroll on mobile -->
		<!-- <div class=" hidden overflow-x-auto px-4 sm:mx-0 sm:block sm:px-0">
			<table
				class="w-full min-w-full border-separate border-spacing-0 border-gray-200 text-left dark:border-gray-700"
			>
				<thead>
					<tr>
						<th
							class="sticky left-0 min-w-[120px] border-b border-gray-200 bg-white dark:border-gray-700 dark:bg-gray-900"
						>
							<span class="sr-only">Feature</span>
						</th>
						{#each tierNames as tierName}
							<th
								class="text-headline min-w-[100px] border-b border-gray-200 p-4 text-start font-normal dark:border-gray-700"
							>
								{tierName}
							</th>
						{/each}
					</tr>
				</thead>
				<tbody>
					{#each features as feature}
						<tr>
							<td class="text-caption">
								{feature.name}
							</td>
							{#each tierNames as tierName}
								<td
									class="min-w-[100px] border-b border-gray-200 p-4 text-start text-gray-600 dark:border-gray-700 dark:text-gray-300"
								>
									{#if typeof feature.tiers[tierName] === "boolean"}
										{#if feature.tiers[tierName]}
											<IconCheck
												class="text-primary-600 dark:text-primary-400 mx-auto size-5 sm:mx-0"
											/>
										{:else}
											<IconX class="mx-auto size-5 text-gray-400 sm:mx-0" />
										{/if}
									{:else}
										{feature.tiers[tierName]}
									{/if}
								</td>
							{/each}
						</tr>
					{/each}
				</tbody>
			</table>
		</div> -->

		<!-- Mobile feature comparison (alternative view for very small screens) -->
		<div>
			<!-- Universal pricing comparison for mobile -->
			<div class="overflow-x-auto">
				<table class="w-full border-collapse">
					<!-- Sticky header with tier names -->
					<thead class="border-border sticky top-0 z-10 border-b">
						<tr>
							<th class="min-w-[120px] py-3 text-left">
								<span class="sr-only">Feature</span>
							</th>
							{#each tierNames as tierName, i}
								<th class="text-caption min-w-[100px] py-3 text-left dark:text-white">
									{tierName}
								</th>
							{/each}
						</tr>
					</thead>
					<tbody class="divide-border divide-y">
						{#each features as feature}
							<tr>
								<td class="text-body py-3 pr-8 font-medium lg:pr-0 dark:text-white">
									{feature.name}
								</td>
								{#each tierNames as tierName, i}
									<td class="py-3">
										{#if typeof feature.tiers[tierName] === "boolean"}
											{#if feature.tiers[tierName]}
												<IconCheck class="text-primary-900 dark:text-primary-400 size-5" />
											{:else}
												<IconX class="size-5 text-gray-400" />
											{/if}
										{:else}
											<span class="text-callout font-medium text-gray-700 dark:text-gray-300">
												{feature.tiers[tierName]}
											</span>
										{/if}
									</td>
								{/each}
							</tr>
						{/each}
					</tbody>
				</table>
			</div>
		</div>
	</div>
	<LogoScroller />
</section>

<style lang="postcss">
	@reference '../../../app.css';

	:global(number-flow-svelte)::part(suffix) {
		@apply text-sm text-gray-400 dark:text-gray-500;
	}
</style>
