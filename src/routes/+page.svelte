<script lang="ts">
	// Components
	import Summary from "$lib/components/layout/Summary.svelte";
	import Features from "$lib/components/layout/Features.svelte";
	import Testimonials from "$lib/components/layout/Testimonials.svelte";
	import CallToAction from "$lib/components/layout/CallToAction.svelte";
	import AboutTeaser from "$lib/components/layout/AboutTeaser.svelte";
	import LogoScroller from "$lib/components/layout/LogoScroller.svelte";
	import CenteredTextOnlyHero from "$lib/components/layout/hero-sections/CenteredTextOnlyHero.svelte";
	import UseCases from "$lib/components/layout/UseCases.svelte";
</script>

<CenteredTextOnlyHero
	title="Ship AI features in minutes, not months"
	subtitle="Transform complex AI workflows into deployable solutions with simplified agent architecture. Stop letting 3-6 month development cycles delay your product releases."
	imageSrc="/generated/image-a-group-of-people-in-a-minimalist-contro.webp"
/>
<LogoScroller label="" />

<Summary
	title="What we do"
	text="Agentify transforms complex AI workflows into deployable solutions through simplified agent architecture. We help SaaS companies ship AI-powered features in minutes instead of months, eliminating the 3-6 month development cycles that delay product releases."
/>

<Testimonials
	testimonials={[
		{
			name: "Neha Raman",
			position: "Product Lead",
			company: "Finetro",
			quote:
				"We shipped our AI onboarding feature in under a week. Before Agentify, this would have taken 3 months minimum and cost us $180K in development resources.",
			image:
				"/generated/image-a-person-sitting-at-a-sleek-modern-desk-.webp"
		},
		{
			name: "Kai Okafor",
			position: "Director of Engineering",
			company: "PulseStack",
			quote:
				"Our engineers saved 4 weeks of sprint time. Agentify eliminated the risk of building AI infrastructure from scratch while cutting our prototype costs by 85%.",
			image:
				"/generated/image-a-small-team-collaborating-in-a-minimali.webp"
		},
		{
			name: "Valencia Torres",
			position: "VP of Product",
			company: "DataFlow Systems",
			quote:
				"We avoided hiring two additional AI engineers, saving us $320K annually. The drag-and-drop interface meant zero technical debt and faster feature iteration.",
			image:
				"/generated/image-a-group-of-professionals-engaged-in-a-th.webp"
		}
	]}
/>

<Features
	title="Why Agentify"
	subtitle="Deploy intelligent AI agents in minutes with our simplified architecture that transforms complex workflows into drag-and-drop solutions"
	features={[
		{
			title: "Drag-and-drop agent builder",
			description: "Skip months of complex AI development with our visual interface that lets product teams create powerful agents without coding expertise."
		},
		{
			title: "Pre-built workflow templates",
			description: "Launch faster with battle-tested templates designed specifically for Series A-C SaaS companies to accelerate feature releases."
		},
		{
			title: "Simplified agent architecture",
			description: "Transform complex AI workflows into deployable solutions with our streamlined architecture that reduces implementation time by 90%."
		},
		{
			title: "Rapid deployment pipeline",
			description: "Ship AI-powered features in minutes, not months, with automated deployment that integrates seamlessly into existing development workflows."
		},
		{
			title: "Enterprise-ready security",
			description: "Deploy with confidence using industry-standard security protocols designed for mid-market SaaS companies handling sensitive customer data."
		},
		{
			title: "Scalable agent management",
			description: "Manage thousands of deployed agents through a unified dashboard that grows with your product and user engagement needs."
		}
	]}
/>

<UseCases
	title="Use Cases"
	subtitle="Real-world applications transforming how SaaS companies deploy AI"
	useCases={[
		{
			title: "Accelerate feature launches from months to minutes",
			description: "When product roadmaps demand AI-powered features but development cycles stretch 3-6 months, Agentify's drag-and-drop builder helps product managers ship intelligent onboarding, personalization, and recommendation features in under a week.",
			image: "/generated/image-a-poised-individual-standing-confidently.webp",
			link: {
				href: "/use-cases/rapid-feature-deployment",
				label: "Learn more"
			}
		},
		{
			title: "Scale engineering velocity without technical debt",
			description: "Growing SaaS teams need AI capabilities without hiring specialized engineers or building complex infrastructure. Agentify's pre-built templates and simplified architecture eliminate technical debt while reducing AI development costs by 85%.",
			image: "/generated/image-two-colleagues-collaborating-in-a-contem.webp",
			link: {
				href: "/use-cases/engineering-acceleration",
				label: "Learn more"
			}
		},
		{
			title: "Transform customer support with intelligent automation",
			description: "When support volumes overwhelm teams and response times suffer, Agentify helps deploy smart routing agents, automated resolution workflows, and predictive support that improves customer satisfaction while reducing manual work.",
			image: "/generated/image-a-scene-of-a-professional-team-working-t.webp",
			link: {
				href: "/use-cases/intelligent-customer-support",
				label: "Learn more"
			}
		}
	]}
/>
<AboutTeaser />
<CallToAction />
