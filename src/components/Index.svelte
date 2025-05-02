<script>
	import Footer from "$components/Footer.svelte";
	import Hero from "$components/helpers/Hero.svelte";
	import Scrolly from "$components/helpers/Scrolly.svelte";

	let value = $state();

	// Define individual steps
	const explanation = [
		"Everyone in this world has one thing in common, time – with 24 hours a day, 7 days a week, 52 weeks a year. But the way we use time creates all the difference in this world. Age, sex, income, geography, education, relationships and a lot of factors decide how and who we all spend time with. In this scrolly, we will explore how Americans spend their time, by gender and by age.",
		"Men in their middle ages spent more time alone than women.",
	];

</script>

<Hero
	hed="How Do Americans Spend Their Time?"
	byline="By Inaara Gangji, Anasooya Thorakkattu, WanYu Yao"
	date="May 5, 2025"
	src="/demo/assets/cover-image.svg"
	alt="How Americans Spend Their Time Cover Image"
/>

<div class="container">
	<section id="scrolly">
		<div class="sticky">
			{#if value === 0}
				<img src="/demo/assets/step0-bg.jpeg" alt="Step 0 Background" class="media-img" />
			{:else if value === 1 }
				<iframe
					src="https://ourworldindata.org/grapher/who-americans-spend-their-time-with?tab=line"
					loading="lazy"
					allow="web-share; clipboard-write"
					style="width: 100%; height: 100%; border: 0"
					class="media-iframe">
				</iframe>
			{/if}
		</div>

		<div class="spacer"></div>

		<Scrolly bind:value>
			{#each explanation as text, i}
				{@const active = value === i}
				<div class="step" class:active>
					<p>{text}</p>
				</div>
			{/each}
		</Scrolly>

		<div class="spacer"></div>
	</section>
</div>


<Footer />

<style>

	.media-img,
	.media-iframe {
		max-width: 100%;
		width: 100%;
		height: auto;
		display: block;
		margin-left: auto;
		margin-right: auto;
	}

	.container {
		background-color: #F2D49E;
	}

	.sticky {
		position: sticky;
		top: 4em;
	}

	.spacer {
		height: 75vh;
	}

	.step {
		max-width: 50em;
		margin: 80vh auto;
		background: var(--color-gray-100);
		text-align: center;
	}

	.step p {
		padding: 1rem;
	}

	span {
		background: var(--color-mark);
		padding: 0 8px;
	}

</style>
