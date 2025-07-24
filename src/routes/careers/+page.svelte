<script lang="ts">
	// Types

	// Components
	import SectionHeader from "$lib/components/layout/SectionHeader.svelte";
	import Culture from "$lib/components/layout/Culture.svelte";
	import Testimonials from "$lib/components/layout/Testimonials.svelte";
	import SecondaryHero from "$lib/components/layout/hero-sections/SecondaryHero.svelte";
	import Card from "$lib/components/ui/Card.svelte";
	import JobList, { type JobOpening } from "./JobList.svelte";

	// Icon components - temporary until unplugin-icons is fixed
	import IconBriefcase from "$lib/components/icons/IconBriefcase.svelte";
	import IconUsers from "$lib/components/icons/IconUsers.svelte";
	import IconHeart from "$lib/components/icons/IconHeart.svelte";
	import IconGlobe from "$lib/components/icons/IconGlobe.svelte";

	// Constants
	const SECTION_BASE_CLASSES = "section-py section-px container mx-auto";
	const GRADIENT_BG_CLASSES =
		"bg-gradient-to-br from-gray-50 to-gray-100 dark:from-gray-900 dark:to-gray-800";
	const ICON_CONTAINER_CLASSES =
		"bg-primary-50 text-primary-600 dark:bg-primary-950 dark:text-primary-400 flex items-center justify-center rounded-full";

	const benefits = [
		{
			title: "Build product that launches—fast",
			description: "At Agentify, we simplify complexity so you can build things that ship. You'll work on features that move from idea to production in days, not quarters.",
			icon: IconBriefcase
		},
		{
			title: "Work on the future of AI",
			description: "Our drag-and-drop agent builder turns AI from a research project into a product feature. You'll help teams go from proof-of-concept to production without the bottlenecks.",
			icon: IconUsers
		},
		{
			title: "Grow in a $297B market",
			description: "AI is big and only getting bigger. We're building the tools developers actually want to use—yours could be the next one adopted by 100,000+ teams.",
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
			title: "AI/ML Engineer",
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
			title: "DevOps Engineer",
			department: "Engineering",
			location: "Remote",
			type: "Full-time",
			url: "#"
		},

		// Design
		{
			title: "Product Designer",
			department: "Design",
			location: "Remote",
			type: "Full-time",
			url: "#"
		},
		{
			title: "UX Engineer",
			department: "Design",
			location: "Remote",
			type: "Full-time",
			url: "#"
		},

		// Product
		{
			title: "Product Manager - AI Tools",
			department: "Product",
			location: "Remote",
			type: "Full-time",
			url: "#"
		},
		{
			title: "Technical Product Manager",
			department: "Product",
			location: "Remote",
			type: "Full-time",
			url: "#"
		},

		// Marketing
		{
			title: "Developer Relations",
			department: "Marketing",
			location: "Remote",
			type: "Full-time",
			url: "#"
		},
		{
			title: "Content Marketing Manager",
			department: "Marketing",
			location: "Remote",
			type: "Full-time",
			url: "#"
		}
	];

	const employeeTestimonials = [
		{
			name: "Sarah Kim",
			position: "Senior Software Engineer",
			company: "Engineering Team",
			quote:
				"The growth opportunities here are incredible. In just 18 months, I've led three major features from concept to production and mentored two junior developers. Our engineering culture prioritizes learning—we have dedicated time for exploring new technologies and contributing to open source projects.",
			image:
				"/generated/image-a-professional-asian-woman-with-a-confid.webp"
		},
		{
			name: "Marcus Thompson",
			position: "Senior Product Manager",
			company: "Product Team",
			quote:
				"What I love most is how we balance ambitious goals with sustainable work practices. We ship fast but never at the expense of quality or team wellbeing. The collaborative environment means I'm constantly learning from brilliant engineers, designers, and fellow PMs who challenge my thinking every day.",
			image:
				"/generated/image-a-professional-black-man-in-an-office-se.webp"
		},
		{
			name: "Isabella Rodriguez",
			position: "Junior UX Designer",
			company: "Design Team",
			quote:
				"Starting my career at Agentify has been transformative. The mentorship program paired me with a senior designer who meets with me weekly, and I've already contributed to user research and interface design for our core agent builder. The company invests in junior talent—I feel valued, not overlooked.",
			image:
				"/generated/image-a-professional-latina-designer-smiling-c.webp"
		}
	];

	const processSteps = [
		{
			step: 1,
			title: "Apply online",
			description: "Share your resume and let us know why you're interested in joining Agentify."
		},
		{
			step: 2,
			title: "Intro call",
			description: "A 30-minute conversation to get to know each other and discuss the role."
		},
		{
			step: 3,
			title: "Project preview",
			description: "A live session or simple take-home to show how you think and approach problems."
		},
		{
			step: 4,
			title: "Team chat",
			description: "Meet the people you'd work with and ask them anything about the role or company."
		},
		{
			step: 5,
			title: "Decision",
			description: "We'll follow up within a few days—no long waits or uncertainty."
		}
	];

	const values = [
		{
			icon: IconBriefcase,
			title: "Build together, ship fast",
			description: "We collaborate closely and place high value on speed and execution—we ship often and iterate quickly."
		},
		{
			icon: IconHeart,
			title: "Clarity over chaos",
			description: "We simplify complexity for users and for ourselves. Clear thinking and communication help us build better."
		},
		{
			icon: IconUsers,
			title: "Ownership over titles",
			description: "We care more about initiative than job descriptions. If something matters, it's yours to lead."
		},
		{
			icon: IconGlobe,
			title: "Developer-first by default",
			description: "We build tools we'd want to use. Simplicity, flexibility, and great UX guide everything we design."
		}
	];
</script>

<!-- Hero Section -->

<SecondaryHero
	title="Build the future of AI automation"
	subtitle="Join a team of brilliant engineers, designers, and product minds who are transforming how developers build with AI. We're creating tools that turn complex workflows into simple, deployable solutions."
	imageSrc="/generated/image-a-diverse-group-of-professionals-collabo.webp"
/>

<!-- Why Join Us Section -->
<section class={SECTION_BASE_CLASSES}>
	<SectionHeader title="Why join us?" subtitle="No hype. Just real outcomes" />

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

		<div class="grid gap-8 md:grid-cols-2 lg:grid-cols-5">
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
