<script lang="ts">
	// Types
	import type { PageProps } from "./$types";

	// Components
	import Hero from "$lib/components/layout/hero-sections/Hero.svelte";

	import Summary from "$lib/components/layout/Summary.svelte";
	import Features from "$lib/components/layout/Features.svelte";
	import Testimonials from "$lib/components/layout/Testimonials.svelte";
	import CallToAction from "$lib/components/layout/CallToAction.svelte";

	// Props
	const { data }: PageProps = $props();
</script>

{#if data.hero}
<Hero
	title={data.hero.title}
	subtitle={data.hero.subtitle}
	callsToAction={data.hero.callsToAction}
/>
{/if}

{#if data.summary}
<Summary title={data.summary.title} text={data.summary.text} />
{/if}

{#if data.testimonials}
<Testimonials testimonials={data.testimonials.map(t => ({
	name: t.author,
	position: t.role,
	company: '',
	quote: t.quote,
	image: t.imageSrc
}))} />
{/if}

{#if data.features}
<Features
	title={data.features.title}
	subtitle={data.features.subtitle}
	features={data.features.items.map(item => ({
		...item,
		icon: undefined // Convert string icon to undefined since Features expects ComponentType
	}))}
/>
{/if}

{#if data.cta}
	<CallToAction
		title={data.cta.title}
		subtitle={data.cta.subtitle}
		description={data.cta.description}
		callsToAction={data.cta.callsToAction}
	/>
{/if}
