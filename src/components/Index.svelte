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

	<div class="text">
		<p>We collected two stories from single women.</p>
		<!-- First Profile -->
		<div class="container-row">
			<!-- Left column: profile image and audio player -->
			<div class="media-column">
				<img src="/demo/assets/Annie.jpeg" alt="Annie Chang" class="profile-img" />
				<audio controls class="audio">
  					<source src="/demo/assets/annie-intv.mp3" type="audio/mpeg" />
				</audio>
			</div>
		
			<!-- Right column: text content -->
			<div class="text-column">
				<h3>Annie Chang</h3>
				<p>
					Lorem ipsum dolor sit amet consectetur adipisicing elit. Necessitatibus impedit delectus cum doloremque ea perspiciatis cumque nam, esse reiciendis laboriosam iusto autem sunt ipsa odit eum voluptates aliquid? Voluptatem, cum?
				</p>
				<p>
					Lorem ipsum dolor, sit amet consectetur adipisicing elit. Temporibus magnam ab rerum pariatur laudantium est eum. Dolores asperiores aliquam iusto saepe voluptate libero excepturi. Iure minus harum fuga ullam. Doloribus.
				</p>
				<p>
					Lorem ipsum dolor sit amet consectetur adipisicing elit. Accusamus, quas. Optio incidunt repudiandae, voluptatem temporibus ducimus hic voluptatibus repellendus quasi sed quisquam fuga laborum ullam, quis quae deserunt ex aperiam!
				</p>
			</div>
		</div>

		<!-- Second Profile -->

		<div class="container-row">
			<!-- Left column: profile image and audio player -->
			<div class="media-column">
				<img src="/demo/assets/grandma.jpeg" alt="Grandma" class="profile-img" />
				<audio controls class="audio">
  					<source src="/demo/assets/annie-intv.mp3" type="audio/mpeg" />
				</audio>
			</div>
		
			<!-- Right column: text content -->
			<div class="text-column">
				<h3>Grandma</h3>
				<p>
					Lorem ipsum dolor sit amet consectetur adipisicing elit. Necessitatibus impedit delectus cum doloremque ea perspiciatis cumque nam, esse reiciendis laboriosam iusto autem sunt ipsa odit eum voluptates aliquid? Voluptatem, cum?
				</p>
				<p>
					Lorem ipsum dolor, sit amet consectetur adipisicing elit. Temporibus magnam ab rerum pariatur laudantium est eum. Dolores asperiores aliquam iusto saepe voluptate libero excepturi. Iure minus harum fuga ullam. Doloribus.
				</p>
				<p>
					Lorem ipsum dolor sit amet consectetur adipisicing elit. Accusamus, quas. Optio incidunt repudiandae, voluptatem temporibus ducimus hic voluptatibus repellendus quasi sed quisquam fuga laborum ullam, quis quae deserunt ex aperiam!
				</p>
			</div>
		</div>
	</div>
		

	<div class="text">
		<h3>So why do women tend to stay alone during their old ages?</h3>
		<p>The average life expectancy of women in the U.S. is 80.2 years, while for men it's only 74.8 years. So, in a heterosexual relationship where both partners are the same age and get married in middle age (let’s say around 40), the woman will, on average, live about 5.4 years longer than her partner. So, if they both reach their 40s and stay healthy into older age, she is likely to outlive him by over 5 years.</p>

		<!-- insert a datawrapper iframe here -->

		<h3>So what if she gets remarried?</h3>
		<p>The average remarriage rate of women after 55 years of age is 1.13 times less likely than men. That means for every 113 men that get remarried, only 100 women do on average.</p>
		<!-- insert a datawrapper iframe here -->
	</div>
</div>


<Footer />

<style>

	.container-row {
		display: flex;
		align-items: stretch; /* Ensure both columns align vertically */
		gap: 2rem;
		max-width: 960px;
		margin: 2rem auto;
	}

	/* Left column: image and audio vertically stacked */
	.media-column {
		display: flex;
		flex-direction: column;
		justify-content: space-between; /* Spread image and audio */
		width: 40%;
	}

	/* Image with flexible height and preserved aspect ratio */
	.profile-img {
		width: 100%;
		height: 80%;
		flex-grow: 1;
		object-fit: cover;
		margin-bottom: 1rem;
		border-radius: 8px; /* optional: rounded corners */
	}

	/* Audio player sits below the image */
	.audio {
		width: 100%;
	}

	/* Right column: text content */
	.text-column {
		width: 60%;
		display: flex;
		flex-direction: column;
		justify-content: center;
	}



	.h3{
		max-width: 100%;
		margin: auto auto;
	}

	.text {
		max-width: 40rem;
		padding: 16px;
		margin: auto auto;
	}

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
