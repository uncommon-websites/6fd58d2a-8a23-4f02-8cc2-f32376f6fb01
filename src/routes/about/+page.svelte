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
			title: "Simplicity first",
			description: "We believe powerful AI shouldn't require complex infrastructure. Every feature we build removes complexity rather than adding it."
		},
		{
			title: "Developer empathy",
			description: "Having felt the pain of lengthy AI development cycles ourselves, we design solutions that respect your time and expertise."
		},
		{
			title: "Ship fast, iterate faster",
			description: "Great products emerge from rapid experimentation. We enable teams to deploy AI agents in minutes and improve them continuously."
		}
	];
</script>

<SecondaryHero
	title="Transforming AI automation"
	subtitle="from complex to simple"
	imageSrc="/generated/image-a-diverse-group-of-professionals-engaged.webp"
/>

<!-- Story Section -->
<Story
	paragraphs={[
		"Product teams wanted AI features, but months-long development cycles kept delaying launches. We saw talented engineers wrestling with complex AI infrastructure instead of building what users actually needed. There had to be a better way.",
		"Agentify was born from this frustration. We believed that deploying AI shouldn't require rebuilding your entire tech stack or hiring specialized teams. By transforming complex workflows into drag-and-drop interfaces, we turned what used to take 6 months into a 6-minute process.",
		"Today, product managers at Series A-C SaaS companies use Agentify to ship AI-powered features that drive real user engagement. We've simplified the complex so teams can focus on what matters most: creating experiences their users love."
	]}
/>

<!-- Our Culture Section -->
<Culture {values} />

<!-- StakeholderGrid Section -->
<StakeholderGrid
	stakeholderType="team"
	title="Our team."
	subtitle="Your partners in innovation."
	stakeholders={[
		{
			name: "Alex Morgan",
			position: "Founder & CEO",
			bio: "Started the company with a vision to transform the industry through innovative solutions.",
			image:
				"https://images.unsplash.com/photo-1560250097-0b93528c311a?ixlib=rb-4.0.3&ixid=M3wxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHx8fA%3D%3D&auto=format&fit=crop&w=774&q=80"
		},
		{
			name: "Jamie Chen",
			position: "Chief Design Officer", 
			bio: "Award-winning designer with a passion for creating intuitive and beautiful experiences.",
			image:
				"https://images.unsplash.com/photo-1573496359142-b8d87734a5a2?ixlib=rb-4.0.3&ixid=M3wxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHx8fA%3D%3D&auto=format&fit=crop&w=776&q=80"
		},
		{
			name: "Taylor Wright",
			position: "Head of Engineering",
			bio: "Technology enthusiast focused on building scalable systems that make a difference.",
			image:
				"https://images.unsplash.com/photo-1580489944761-15a19d654956?ixlib=rb-4.0.3&ixid=M3wxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHx8fA%3D%3D&auto=format&fit=crop&w=774&q=80"
		}
	]}
/>

<StakeholderGrid
	stakeholderType="investor"
	title="Backed by the best."
	subtitle="Point Nine, TSIC and others"
	stakeholders={[
		{
			name: "Point Nine Capital",
			image: "https://cdn.brandfetch.io/pointnine.com/w/400/h/400/logo?c=1id_elLz2Bd5Ej-dWo7"
		},
		{
			name: "TSIC Ventures",
			image: "https://cdn.brandfetch.io/tiny.vc/w/400/h/400/logo?c=1a2b3c4d5e"
		},
		{
			name: "Sequoia Capital",
			image: "https://cdn.brandfetch.io/sequoiacap.com/w/400/h/400/logo"
		}
	]}
/>

<!-- CTA Section -->
<CallToAction
	title="Ship AI features that users love"
	subtitle="Without the 6-month development cycle"
	description="Join product managers at Series A-C SaaS companies who've already discovered how Agentify transforms complex AI workflows into simple drag-and-drop experiences. Stop letting AI complexity delay your product roadmap."
/>
