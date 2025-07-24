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
	// Icon components
	function IconCheck() {
		return `<svg width="16" height="16" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2" stroke-linecap="round" stroke-linejoin="round"><path d="M20 6 9 17l-5-5"/></svg>`;
	}
	function IconX() {
		return `<svg width="16" height="16" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2" stroke-linecap="round" stroke-linejoin="round"><path d="M18 6 6 18"/><path d="m6 6 12 12"/></svg>`;
	}
	import NumberFlow from "@number-flow/svelte";
	import LogoScroller from "./LogoScroller.svelte";

	// Props
	const {
		title = "Scale your AI automation",
		subtitle = "From rapid prototyping to enterprise deployment — choose the plan that accelerates your AI journey",
		tierNames = ["Developer", "Team", "Enterprise"],
		features = [
			{
				name: "AI agents per month",
				tiers: {
					Developer: "100",
					Team: "1,000",
					Enterprise: "Unlimited"
				}
			},
			{
				name: "Team members",
				tiers: {
					Developer: "3",
					Team: "15",
					Enterprise: "Unlimited"
				}
			},
			{
				name: "Agent templates",
				tiers: {
					Developer: "50+",
					Team: "200+",
					Enterprise: "500+"
				}
			},
			{
				name: "Drag-and-drop builder",
				tiers: {
					Developer: true,
					Team: true,
					Enterprise: true
				}
			},
			{
				name: "API integrations",
				tiers: {
					Developer: "10",
					Team: "100",
					Enterprise: "Unlimited"
				}
			},
			{
				name: "Deployment environments",
				tiers: {
					Developer: "Development",
					Team: "Dev + Staging",
					Enterprise: "Multi-environment"
				}
			},
			{
				name: "Analytics & monitoring",
				tiers: {
					Developer: "Basic",
					Team: "Advanced",
					Enterprise: "Enterprise"
				}
			},
			{
				name: "Version control",
				tiers: {
					Developer: false,
					Team: true,
					Enterprise: true
				}
			},
			{
				name: "Custom model support",
				tiers: {
					Developer: false,
					Team: "OpenAI, Anthropic",
					Enterprise: "Any model"
				}
			},
			{
				name: "Support response time",
				tiers: {
					Developer: "48 hours",
					Team: "12 hours",
					Enterprise: "4 hours"
				}
			},
			{
				name: "SSO & advanced security",
				tiers: {
					Developer: false,
					Team: false,
					Enterprise: true
				}
			},
			{
				name: "Dedicated success manager",
				tiers: {
					Developer: false,
					Team: false,
					Enterprise: true
				}
			},
			{
				name: "SLA guarantee",
				tiers: {
					Developer: false,
					Team: "99.5%",
					Enterprise: "99.9%"
				}
			}
		],
		tiers = [
			{
				name: "Developer",
				monthlyPrice: 29,
				yearlyPrice: 24, // ~17% savings
				description: "Perfect for product managers testing AI automation concepts",
				features: [
					"100 AI agents per month",
					"50+ pre-built templates",
					"Drag-and-drop agent builder",
					"Up to 3 team members",
					"10 API integrations",
					"Basic analytics",
					"Community support"
				],
				cta: {
					label: "Start free trial",
					href: "/signup?plan=developer"
				}
			},
			{
				name: "Team",
				monthlyPrice: 149,
				yearlyPrice: 124, // ~17% savings
				description: "For growing teams shipping AI-powered features to production",
				features: [
					"1,000 AI agents per month",
					"200+ pre-built templates",
					"Advanced workflow builder",
					"Up to 15 team members",
					"100 API integrations",
					"Version control & rollbacks",
					"Staging environments",
					"Advanced analytics",
					"Priority support"
				],
				cta: {
					label: "Start free trial",
					href: "/signup?plan=team"
				},
				highlight: true
			},
			{
				name: "Enterprise",
				monthlyPrice: null,
				yearlyPrice: null,
				description: "For organizations deploying AI at scale with custom requirements",
				features: [
					"Unlimited AI agents",
					"500+ enterprise templates",
					"Custom model integration",
					"Unlimited team members",
					"Multi-environment deployment",
					"SSO & advanced security",
					"Custom integrations",
					"Dedicated success manager",
					"99.9% SLA guarantee",
					"On-premise deployment options"
				],
				cta: {
					label: "Contact sales",
					href: "/contact"
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
			<div class="inline-flex items-center rounded-full bg-gray-200 p-0.5 gap-0.5">
				<button
					class="rounded-full px-4 py-1.5 text-sm font-semibold transition-all duration-200 {!annual ? 'bg-white text-gray-900 shadow-sm' : 'text-gray-600 hover:text-gray-900'}"
					onclick={() => (annual = false)}
				>
					Monthly
				</button>
				<button
					class="rounded-full px-4 py-1.5 text-sm font-semibold transition-all duration-200 {annual ? 'bg-white text-gray-900 shadow-sm' : 'text-gray-600 hover:text-gray-900'}"
					onclick={() => (annual = true)}
				>
					Annual <span class="text-xs ml-1 text-gray-500">Save 17%</span>
				</button>
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
								<span class="text-primary-600 dark:text-primary-400 size-5 flex-shrink-0">{@html IconCheck()}</span>
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
												<span class="text-primary-900 dark:text-primary-400 size-5 flex-shrink-0">{@html IconCheck()}</span>
											{:else}
												<span class="size-5 text-gray-400 flex-shrink-0">{@html IconX()}</span>
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
