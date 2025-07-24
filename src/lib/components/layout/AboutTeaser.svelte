<!--
@component AboutTeaser
A minimalist teaser for the about page.
-->
<script lang="ts">
	// Types
	type TeamMember = {
		name: string;
		role: string;
		image: string;
	};

	// Components
	import Button from "../ui/Button.svelte";
	import ScrollText from "./sub/ScrollText.svelte";

	// State
	let sectionRef: HTMLElement;

	let props = $props();

	// Data
	const teamMember: TeamMember = {
		name: "Sarah Chen",
		role: "Founder & CEO",
		image:
			"/generated/image-a-professional-headshot-of-a-confident-e.webp"
	};
</script>

<section bind:this={sectionRef} {...props}>
	<div class="section-px section-py container mx-auto">
		<div class="relative mx-auto grid max-w-2xl place-items-center gap-16">
			<ScrollText
				class="text-title1 text-center"
				text={`"After watching countless SaaS teams struggle with 6-month AI development cycles, I knew there had to be a better way. We built Agentify to eliminate the complexity barrier and help product managers ship intelligent features in minutes, not months."`}
			/>

			<!-- Team Member & CTA Section -->
			<div class="grid items-center gap-8 dark:border-gray-800">
				<div class="flex items-center justify-start gap-4">
					<img
						src={teamMember.image}
						alt={teamMember.name}
						class="size-12 rounded-full object-cover"
					/>
					<div>
						<div class="text-callout">{teamMember.name}</div>
						<div class="text-caption text-emphasis-low">{teamMember.role}</div>
					</div>
					<Button href="/about" variant="secondary" size="sm" class="ml-8">Read more</Button>
				</div>
			</div>
		</div>
	</div>
</section>
