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
			name: "Mason Liu",
			position: "Head of Product",
			company: "Flowy",
			quote:
				"We shipped our first AI feature in 6 days. Before Agentify, it took 3 months just to scope a prototype.",
			image: "/generated/image-an-asian-woman-in-her-30s-wearing-a-smar.webp"
		},
		{
			name: "Caitlyn Solace",
			position: "Engineering Manager",
			company: "Stanza",
			quote:
				"The drag-and-drop builder was a game changer—our PMs now design 80% of AI workflows without us.",
			image: "/generated/image-a-confident-hispanic-woman-in-her-30s-we.webp"
		},
		{
			name: "Theo Vasquez",
			position: "VP of Customer Experience",
			company: "Loopdesk",
			quote:
				"Agentify cut our support response time by 63%. It's like having a full-time junior agent in every inbox.",
			image: "/generated/image-a-focused-black-man-in-his-40s-wearing-a.webp"
		}
	]}
/>

<CallToAction />
