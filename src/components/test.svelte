<script>
	import Scrolly from '$components/helpers/Scrolly.svelte'; // adjust if needed

	let value1 = $state();
	let value2 = $state();
	let value3 = $state();

	const paragraphs1 = [
		"Paragraph 1: This is the beginning of the story. Scroll to see more.",
		"Paragraph 2: Here's the continuation of the story with more details."
	];

	const paragraphs2 = [
		"Paragraph 3: This is the next section with a new image.",
		"Paragraph 4: More insight continues here."
	];

	const paragraphs3 = [
		"Paragraph 5: This is the final section of the story.",
		"Paragraph 6: Thank you for scrolling through!"
	];
</script>

<style>
	section {
		display: flex;
		gap: 2rem;
		padding: 2rem 2rem 8rem;
	}

	.left-text {
		flex: 1;
	}

	.right-column {
		flex: 1;
		position: sticky;
		top: 0;
		height: 100vh;
		display: flex;
		align-items: center;
		justify-content: center;
	}

	img {
		max-width: 100%;
		max-height: 90vh;
		object-fit: contain;
		border: 2px solid #ccc;
		border-radius: 8px;
		transition: transform 0.3s ease;
	}


	.step {
		margin: 80vh 0;
		font-size: 1.2rem;
		background: #f4f4f4;
		padding: 1rem;
		border-radius: 6px;
		transition: background 0.3s;
	}

	.step.active {
		background: #e0f7fa;
	}

	.text {
		font-size: 1.2rem;
		line-height: 1.5;
		margin: 4rem 2rem;
		max-width: 60ch;
	}
</style>

<section>
	<div class="left-text">
		<Scrolly bind:value={value97}>
			{#each paragraphs97 as text, i}
				<div class="step" class:active={value2 === i}>
					<p>{text}</p>
				</div>
			{/each}
		</Scrolly>
	</div>

	<div class="right-column" style="background-image: url('/demo/assets/time-bg.jpeg');">
		<div class="illustration">
			<img>
	</div>
</section>


<!-- Before scrollytelling -->
<div class="text">
	<p>This is some content before the scrollytelling sections begin.</p>
	<p>Lorem ipsum dolor sit, amet consectetur adipisicing elit. Mollitia ipsam, sit placeat et quibusdam laudantium ducimus error odio maiores ipsa velit nisi sed atque exercitationem quos quia. Vel, est. Magni?</p>
	<p>Lorem ipsum dolor sit amet, consectetur adipisicing elit. A laudantium eum commodi accusantium illo ad necessitatibus impedit! Rerum enim harum ea sint aspernatur possimus alias illum, soluta quisquam aliquid ratione!</p>
	<p>Lorem ipsum dolor, sit amet consectetur adipisicing elit. Hic facilis quis, eveniet eaque tempore maiores dolores cumque soluta in deserunt! Impedit obcaecati, tempora minus illum tempore consequuntur placeat sit pariatur.</p>
	<p>Lorem ipsum dolor, sit amet consectetur adipisicing elit. Quas excepturi, consequatur optio eveniet quasi dicta at quia illum. Adipisci eligendi quas quod nostrum tempora corrupti explicabo vel maxime dolores vitae.</p>
</div>

<!-- Scrollytelling Section 1 -->
<section>
	<div class="left">
		<Scrolly bind:value={value1}>
			{#each paragraphs1 as text, i}
				<div class="step" class:active={value1 === i}>
					<p>{text}</p>
				</div>
			{/each}
		</Scrolly>
	</div>

	<div class="right">
		<img
			src="/demo/assets/7days.png"
			alt="Scrollytelling visual 1"
			class:image-zoom={value1 === 0}
		/>
	</div>
</section>

<!-- Scrollytelling Section 2 -->
<section>
	<div class="left">
		<Scrolly bind:value={value2}>
			{#each paragraphs2 as text, i}
				<div class="step" class:active={value2 === i}>
					<p>{text}</p>
				</div>
			{/each}
		</Scrolly>
	</div>

	<div class="right">
		<img
			src="/demo/assets/24hours.png"
			alt="Scrollytelling visual 2"
			class:image-zoom={value2 === 0}
		/>
	</div>
</section>

<!-- After scrollytelling -->
<div class="text">
	<p>This is some final content after all the scrollytelling is done.</p>
</div>
