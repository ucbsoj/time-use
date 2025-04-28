<script>
	import Footer from "$components/Footer.svelte";
	import Hero from "$components/helpers/Hero.svelte";
	import Scrolly from "$components/helpers/Scrolly.svelte";

	let value = $state();

	const step1 = {
	  type: "text-center",
	  content: "Everyone in this world has one thing in common:"
	};

	const step2 = {
	  type: "sticky-left",
	  content: "TIME."
	};

	const step3 = {
	  type: "split",
	  layout: "scroll-text",
	  text: "24 hours a day",
	  img: {
		src: "/demo/assets/24hours.png",
		alt: "24 hours"
	  }
	};

	const step4 = {
	  type: "split",
	  layout: "scroll-text",
	  text: "7 days a week",
	  img: {
		src: "/demo/assets/7days.png",
		alt: "7 days"
	  }
	};

	const step5 = {
	  type: "split",
	  layout: "scroll-text",
	  text: "365 days a year",
	  img: {
		src: "/demo/assets/365days.png",
		alt: "365 days"
	  }
	};

	const step6 = {
	  type: "text-center",
	  content: "But the way we use time creates all the difference in this world. Age, sex, income, geography, education, relationships and a lot of factors decide how and who we all spend time with."
	};

	const explanation = [step1,  step3, step4, step5, step6];
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
				{:else if value === 1 || value === 2 || value === 3}
					<h2 class="time">Time.</h2>
				{:else if value === 4}			
				{:else if value === 3}

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

	.container{
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
		margin: 80vh 0;
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
