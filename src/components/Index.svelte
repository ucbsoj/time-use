<script>
	import Footer from "$components/Footer.svelte";
	import Hero from "$components/helpers/Hero.svelte";
	import Scrolly from "$components/helpers/Scrolly.svelte";
	import {crossfade} from 'svelte/transition'

	let value1 = $state();
	let value2 = $state();
	let value3 = $state();
	let value4 = $state();
	let value5 = $state();
	let value6 = $state();
	let value7 = $state();
	let value8 = $state();
	// let value97 = $state();
	// let	value98 = $state();
	// let value99 = $state();

	let valueCalendarScroll = $state();


	// First scrollysection for calendar
	const paragraphs97 = [
		`<h3>Everyone has the same 24 hours a day?</h3>
		 <p><a href="https://www.tandfonline.com/doi/abs/10.1080/17516234.2019.1632018?casa_token=7jYJ7gOUwuIAAAAA:MveJfYozt1Tze4mCheA_3T-0Ia65QcJuzR63dTf2jSpy243KPGleAl2KRP-tpbJhRs0NEtuKrdU" target="_blank" rel="noopener noreferrer">A 2019 study</a> titled Education and Gender Gap in Couples’ Time Use: Evidence from China, found that urban married women with equal or higher education than their husbands had greater control over their time, spending more of it on paid work and leisure activities.While married women in rural areas with similar educational qualifications still spend more time on personal and household care and their educational attainment did not change their control on time spent for leisure and paid work.</p>`
	];

	const paragraphs98 = [
		`<h3>Everyone have the same 7 days a week?</h3>
		 <p>In a 2021 research article titled <a href="https://journals.sagepub.com/doi/10.1177/23328584211011608" target="_blank" rel="noopener noreferrer"> Time Poverty and Parenthood: Who Has Time for College? </a> found that student parents in the U.S. with children under 13 had less discretionary free time. They were more likely to study while caring for their children and to enroll part-time compared to students without children. This suggested that student parents may require consideration of time poverty for better college outcomes.</p>`
	];

	const paragraphs99 = [
		`<h3>And everyone has the same 365 days a year?</h3>
		 <p>If we compare that to<a href="https://www.tandfonline.com/doi/abs/10.1080/00346764.2015.1035909?casa_token=cKeBdCFv7QAAAAAA:crRGerzYMNXbl3Ef5vF8OZwQfTeO8VPXU4rmqsS3AqynF7DvC0aF_uDKjFdz4MgRfF9jIr7BbI8" target="_blank" rel="noopener noreferrer">a 2015 research article</a> on Gender Differences in Time Poverty in Rural Mozambique women in impoverished households in Mozambique experience more time poverty compared to men. As the heavy burden of household responsibilities are struck upon women along with care work pushing them to multi-task making them more time-poor compared to men.</p>`
	];

	// Second scrollysection for graphics interpretation

	const paragraphs1 = [
		`<p><a href="https://ourworldindata.org/time-use" target="_blank" rel="noopener noreferrer">Our World Data</a> also released a report in 2020 based on the American Time Use Survey – by using the question "Who was in the room with you?" or "Who accompanied you?” in the ATUS, they investigated how many hours Americans spend alone on average. If people are on a phone or video call, they are not counted as being with someone, unless someone else is in the room with them. On average, older people spend a large amount of time alone.</p>`
	];


	const paragraphs2 = [
		"Annie Chang, 41, a cashier space receptionist in Kaiser Permanente spends her time primarily working, with family and friends and being alone.",
		"Shirley Streshinsky, a 90+ journalist, writer and widow, used to spend most of her time alone at her house in Kensington until recently as she took a fall and broke her arm."
	];

	const paragraphs3 = [
		"Men in their middle ages spent more time alone than women. An average 34-year-old man spends 5 and a half hours alone in their life, while a woman spends that time with their children. In 5.5 hours you could, (finish watching the entire Back to The Future Trilogy, or watch the whole Season 1 of Stranger Things, alone)."		];

	const paragraphs4 = [
		"From age 34-44, most men tend to spend more time with their co-workers than with their partners. This was also the year where men showed the highest labor force participation rate of all age groups than women."
	];

	const paragraphs5 = [
		"At the same time, men after the age of 57 tend to show a continuous growth in the number of hours they spend with their partner going up to as high as 5 and half hours (now they can watch the whole Season 1 of Stranger Things together). This is because they are more likely to get remarried than women.",
		"While a woman spends most of her 30s with their children."
	];

	const paragraphs6 = [
		"Over the past 30 years, children have received increased attention and care, according to Leslie Salzinger, associate professor and chair of Gender and Women’s Studies Department at UC Berkeley. The gap remains largely unchanged in caretaking between men and women, with women taking the brunt of it even though men are spending more time with their children in general. Gender stereotypes are still evident, said Salzinger, despite the emancipation of women.",
		"Women will, in general, also be more alone due to more caregiving responsibilities as they are more likely to be widows and outlive men, according to R. Gordon Rinderknecht, an associate behavioral scientist at RAND, who researches primarily focuses on how people spend their time—especially as it relates to social isolation, loneliness, and inequality."
	];

	const paragraphs7 = [
		`<h3>So why do women tend to stay alone more only when older?</h3>
		<figure class="quote-with-photo">
			<img src="assets/Leslie-photo.jpg" alt="Photo of Expert" class="expert-photo">
			<figcaption>
				<blockquote>
					<p>"[Women] live longer than their male partners and because they don’t have children to care for. I do think stereotypes do give you some information and we know that women spend more time with kids and the divorce rate has increased and women live longer than men, so that over time women are spending more time alone sort of seems baked into those patterns."</p>
					<p class="expert-credit">– Leslie Salzinger, UC Berkeley Professor in Gender Studies</p>
				</blockquote>
			</figcaption>
		</figure>`,
		`<p>Chang says she was more sociable in her 20s – besides working over 40 hours a week – hanging out with friends and her pet. When getting into 30s, she became more isolated but comfortable with the change. “I am very happy being alone as a single person, but sometimes craving to be with other people,” she said.</p>`,
		`<p>Shirley is also quite content and almost used to being alone too although it does take her longer to do things at an older age. When younger, she decided to forego her first marriage for her career because she was young but decided to take on most of the caregiving in her second marriage as her partner traveled. He passed away when she was 68.</p>`
	];


	const paragraphs8 = [
	"Women from the age of 57 start spending less time with a partner, the lowest being only 2.85 hours. Salzinger explained that this is when most partners pass away as women tend to outlive men because of biological reasons, but also sociological reasons such as men doing more physically hazardous jobs."
	];

	

</script>

<Hero
	hed="How Do Americans Spend Their Time?"
	byline="By Inaara Gangji, Anasooya Thorakkattu, WanYu Yao"
	date="May 5, 2025"
	src="assets/cover-image.svg"
	alt="How Americans Spend Their Time Cover Image"
/>


<style>
	/* @css */

	/* CSS for graphics in the last section */
	/* .flourish-text-iframe {
	width: 100%;
	max-width: 800px;
	height: 600px;
	border: none;
	border-radius: 8px;
	box-shadow: 0 2px 12px rgba(0, 0, 0, 0.1);
	margin: 2rem auto;
	display: block;
	} */


	.datawrapper-graphic {
		width: 0; 
		min-width: 100% !important;
		border: none;
		background-color: white
	}

	.container-row {
	display: flex;
	align-items: center;
	max-width: 52em;
	margin: 2em auto;
	gap: 2em; 
	background-color: #FFF5EE;
	border-radius: 5%;
	padding: 2em;
	}

	/* CSS for bios */
	/* Left column: image and audio vertically stacked */
	.media-column {
	display: flex;
	flex-direction: column;
	width: 40%;
	}

	/* Image with preserved aspect ratio */
	.profile-img {
	width: 100%;
	height: auto;
	object-fit: cover;
	}

	/* Audio player sits below the image */
	.audio {
	width: 100%;
	}

	/* Right column: text content */
	.right-inner {
	width: 100%;
	height: 100%;
	display: flex;
	align-items: center;
	justify-content: center;
	}

	.text-column {
	width: 60%;
	display: flex;
	flex-direction: column;
	justify-content: center;
	}


	/* CSS for html scrolling section */
	:global(.quote-with-photo) {
	display: flex;
	align-items: flex-start;
	gap: 1rem;
	margin-top: 1rem;
	}

	:global(.expert-photo) {
		width: 80px;
		height: 100px;
		object-fit: cover;
		border-radius: 30%;
		box-shadow: 0 2px 4px rgba(0, 0, 0, 0.1);
		margin-right: 0.75rem;
		vertical-align: middle;
	} 


	:global(.blockquote) {
		margin: 0;
		font-style: italic;
		color: #444;
	}

	:global(.expert-credit) {
	margin-top: 0.5rem;
	color: #666;
	font-style: normal;
	font-size: 0.9rem;
	}


	/* CSS for scrolling section graphics */
	.flourish-wrapper {
		position: relative;
		width: 100%;
		padding-top: 70%;
	}

	.flourish-embed-iframe {
		position: absolute;
		top: 0;
		left: 0;
		width: 100%;
		height: 100%;
		border: none;
		border-radius: 8px;
		box-shadow: 0 2px 10px rgba(0, 0, 0, 0.1);
	}

	section {
		display: flex;
		gap: 2rem;
		padding: 2rem 2rem 8rem;
	}

	.left {
		flex: 0 0 40%;
		padding-left: 2rem;
	}

	.right {
		flex: 0 0 60%;
		padding: 0 2rem;
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
		transition: transform 0.3s ease;
	}

	.step {
		margin: 80vh 0;
		font-size: 1.2rem;
		background: #fff;
		padding: 1rem;
		transition: background 0.3s;
		border-left: 4px solid #007acc;
		font-family: 'Times New Roman', Times, serif;
	}

	.step.active {
		background: #fff;
		opacity: 0.8;
		border-left: 4px solid #007acc;
	}

	h3{
		max-width: 100%;
		margin: auto auto;
		font-family: 'Times New Roman', Times, serif;
	}

	.text {
		max-width: 40rem;
		padding: 16px;
		margin: auto auto;
		font-family: 'Times New Roman', Times, serif;
		font-size: 1.2rem;
	}

	.container {
		background-color: #F2D49E;
		z-index: 0;
	}
</style>

<!-- Plain Text Before Scrollytelling -->
<div class="container">
	<div class="text">
		<p>Time is the one thing that we all have in common, while also being the one thing we use in completely different ways. The way we use time creates all the difference in this world. Age, sex, income, geography, education, relationships and a lot of factors decide how and who we all spend time with.</p>
		<p>As individuals are trying to manage and find more time in their lives to do different things, it often ignores the broader societal structure that influences time use. Here we are looking into those broader aspects and understand how it influenced people in the US to spend their time.</p>
	</div>


	<!-- Scrollytelling for calendar-->
	<!-- 24hours -->
	<section>
		<div class="left">
			<Scrolly bind:value={valueCalendarScroll}>
				{#each [paragraphs97, paragraphs98, paragraphs99] as paragraph}
					{#each paragraph as text, i}
						<div class="step" class:active={value1 === i}>
							<p>{@html text}</p>
						</div>
					{/each}
				{/each}
			</Scrolly>
		</div>

		<div class="right">
			<div class="right-inner">
				{#if valueCalendarScroll === 0}
					<img src="assets/24hours.png" alt="Scrollytelling visual 1" transition:crossfade/>
				{:else if valueCalendarScroll === 1}
					<img src="assets/7days.png" alt="Scrollytelling visual 1" transition:crossfade/>
				{:else if valueCalendarScroll === 2}
					<img src="assets/year.png" alt="Scrollytelling visual 1" transition:crossfade/>
				{/if}
			</div>
		</div>
	</section>

	{#if valueCalendarScroll !== undefined}
		<audio src="assets/tiktok.mp3" preload="auto" autoplay={true} loop={true}></audio>
	{/if}


<!-- Plain Text - How do we define time alone-->

	<div class="text">
		<h3>Now how do we define time alone?</h3>
		<p><a href="https://www.bls.gov/tus/">The American Time Use Survey </a> "time spent alone" as periods when an individual is physically by themselves, regardless of whether they are engaged in activities such as watching television, reading, or using a computer.</p>
		<p>The way we now spend time alone was also shaped by something monumental we all experienced—together, yet in isolation.</p>
		<!-- pandemic pic -->
		<figure style="text-align: center;">
			<img src="assets/pandemic.jpeg" alt="Pandemic" style="max-width: 100%;" />
			<figcaption style="color: grey;">Image Source: Adobe Stock</figcaption>
		  </figure>		  
		<p>According to the <a href="https://enghinatalay.github.io/ei23.pdf">research at the Federal Reserve Bank of Philadelphia</a> done in 2023, alone time peaked in 2020, with Americans spending nearly 53% of their day alone—driven not just by the pandemic’s second wave, but also by a shifting population. A growing number of older and unmarried individuals accounted for nearly one-third of the overall rise in time spent alone.</p>
		<p>So truly, how much of our daily lives are spent alone in the U.S.? According to the Decennial U.S. censuses from 1790 to 2010 and American Community Surveys (ACS) from 2000 to 2018, this number has consistently increased over time, especially at an older age.</p>
	</div>

	<!-- Interpret Data Scrollytelling Section 2 -->

		<!-- % Americans who live alone, by age -->
		<section>
			<div class="left">
				<Scrolly bind:value={value1}>
					{#each paragraphs1 as text, i}
						<div class="step" class:active={value3 === i}>
							<p>{@html text}</p>
						</div>
					{/each}
				</Scrolly>
			</div>
			
			<div class="right">
				<div class="right-inner">
					<div class="flourish-wrapper">
						<iframe src='https://flo.uri.sh/visualisation/22900966/embed' title='Interactive or visual content' class='flourish-embed-iframe' frameborder='0' scrolling='no' style='width:100%;height:600px;' sandbox='allow-same-origin allow-forms allow-scripts allow-downloads allow-popups allow-popups-to-escape-sandbox allow-top-navigation-by-user-activation'></iframe><div style='width:100%!;margin-top:4px!important;text-align:right!important;'><a class='flourish-credit' href='https://public.flourish.studio/visualisation/22900966/?utm_source=embed&utm_campaign=visualisation/22900966' target='_top' style='text-decoration:none!important'><img alt='Made with Flourish' src='https://public.flourish.studio/resources/made_with_flourish.svg' style='width:105px!important;height:16px!important;border:none!important;margin:0!important;'> </a></div>					
					</div>
				</div>
			</div>
		</section> 
		<!-- All ages time spent -->
		<section>
			<div class="left">
				<Scrolly bind:value={value2}>
					{#each paragraphs2 as text, i}
						<div class="step" class:active={value3 === i}>
							<p>{text}</p>
						</div>
					{/each}
				</Scrolly>
			</div>
			
			<div class="right">
				<div class="right-inner">
					<div class="flourish-wrapper">
						<iframe src='https://flo.uri.sh/visualisation/22999902/embed' title='Interactive or visual content' class='flourish-embed-iframe' frameborder='0' scrolling='no' style='width:100%;height:600px;' sandbox='allow-same-origin allow-forms allow-scripts allow-downloads allow-popups allow-popups-to-escape-sandbox allow-top-navigation-by-user-activation'></iframe><div style='width:100%!;margin-top:4px!important;text-align:right!important;'><a class='flourish-credit' href='https://public.flourish.studio/visualisation/22999902/?utm_source=embed&utm_campaign=visualisation/22999902' target='_top' style='text-decoration:none!important'><img alt='Made with Flourish' src='https://public.flourish.studio/resources/made_with_flourish.svg' style='width:105px!important;height:16px!important;border:none!important;margin:0!important;'> </a></div>
				</div>
			</div>
		</section> 

<!-- Plain text - How men and women in the US spend time -->

	<div class="text">
		<h3>So, how men and women in the US choose to spend their time also differs by age, especially time spent alone?</h3>
	</div>

	<!-- Interpret Data Scrollytelling Section -->

	<!-- Men time spent alone -->
	<section>
		<div class="left">
			<Scrolly bind:value={value3}>
				{#each paragraphs3 as text, i}
					<div class="step" class:active={value3 === i}>
						<p>{text}</p>
					</div>
				{/each}
			</Scrolly>
		</div>
		
		<div class="right">
			<div class="right-inner">
				<div class="flourish-wrapper">
					<iframe src='https://flo.uri.sh/visualisation/22901347/embed' title='Interactive or visual content' class='flourish-embed-iframe' frameborder='0' scrolling='no' style='width:100%;height:600px;' sandbox='allow-same-origin allow-forms allow-scripts allow-downloads allow-popups allow-popups-to-escape-sandbox allow-top-navigation-by-user-activation'></iframe><div style='width:100%!;margin-top:4px!important;text-align:right!important;'><a class='flourish-credit' href='https://public.flourish.studio/visualisation/22901347/?utm_source=embed&utm_campaign=visualisation/22901347' target='_top' style='text-decoration:none!important'><img alt='Made with Flourish' src='https://public.flourish.studio/resources/made_with_flourish.svg' style='width:105px!important;height:16px!important;border:none!important;margin:0!important;'> </a></div>
				</div>
			</div>
		</div>
	</section>

	<!-- Men time spent with coworkers -->

	<section>
		<div class="left">
			<Scrolly bind:value={value4}>
				{#each paragraphs4 as text, i}
					<div class="step" class:active={value2 === i}>
						<p>{text}</p>
					</div>
				{/each}
			</Scrolly>
		</div>

		<div class="right">
			<div class="right-inner">
				<div class="flourish-wrapper">
					<iframe src='https://flo.uri.sh/visualisation/22941340/embed' title='Interactive or visual content' class='flourish-embed-iframe' frameborder='0' scrolling='no' style='width:100%;height:600px;' sandbox='allow-same-origin allow-forms allow-scripts allow-downloads allow-popups allow-popups-to-escape-sandbox allow-top-navigation-by-user-activation'></iframe><div style='width:100%!;margin-top:4px!important;text-align:right!important;'><a class='flourish-credit' href='https://public.flourish.studio/visualisation/22941340/?utm_source=embed&utm_campaign=visualisation/22941340' target='_top' style='text-decoration:none!important'><img alt='Made with Flourish' src='https://public.flourish.studio/resources/made_with_flourish.svg' style='width:105px!important;height:16px!important;border:none!important;margin:0!important;'> </a></div>
				</div>
			</div>
		</div>
	</section>

	<!-- Men time spent with a partner -->

	<section>
	<div class="left">
		<Scrolly bind:value={value5}>
			{#each paragraphs5 as text, i}
				<div class="step" class:active={value3 === i}>
					<p>{text}</p>
				</div>
			{/each}
		</Scrolly>
	</div>

	<div class="right">
		<div class="flourish-wrapper">
			<iframe src='https://flo.uri.sh/visualisation/22941370/embed' title='Interactive or visual content' class='flourish-embed-iframe' frameborder='0' scrolling='no' style='width:100%;height:600px;' sandbox='allow-same-origin allow-forms allow-scripts allow-downloads allow-popups allow-popups-to-escape-sandbox allow-top-navigation-by-user-activation'></iframe><div style='width:100%!;margin-top:4px!important;text-align:right!important;'><a class='flourish-credit' href='https://public.flourish.studio/visualisation/22941370/?utm_source=embed&utm_campaign=visualisation/22941370' target='_top' style='text-decoration:none!important'><img alt='Made with Flourish' src='https://public.flourish.studio/resources/made_with_flourish.svg' style='width:105px!important;height:16px!important;border:none!important;margin:0!important;'> </a></div>		</div>
	</section>

	<!-- Women time spent with children -->
	<section>
		<div class="left">
			<Scrolly bind:value={value6}>
				{#each paragraphs6 as text, i}
					<div class="step" class:active={value3 === i}>
						<p>{text}</p>
					</div>
				{/each}
			</Scrolly>
		</div>
		
		<div class="right">
			<div class="right-inner">
				<div class="flourish-wrapper">
					<iframe src='https://flo.uri.sh/visualisation/22941304/embed' title='Interactive or visual content' class='flourish-embed-iframe' frameborder='0' scrolling='no' style='width:100%;height:600px;' sandbox='allow-same-origin allow-forms allow-scripts allow-downloads allow-popups allow-popups-to-escape-sandbox allow-top-navigation-by-user-activation'></iframe><div style='width:100%!;margin-top:4px!important;text-align:right!important;'><a class='flourish-credit' href='https://public.flourish.studio/visualisation/22941304/?utm_source=embed&utm_campaign=visualisation/22941304' target='_top' style='text-decoration:none!important'><img alt='Made with Flourish' src='https://public.flourish.studio/resources/made_with_flourish.svg' style='width:105px!important;height:16px!important;border:none!important;margin:0!important;'> </a></div>
				</div>
			</div>
		</div>
	</section>

	<!-- Women time spent time with alone -->
	<section>
		<div class="left">
			<Scrolly bind:value={value7}>
				{#each paragraphs7 as text, i}
					<div class="step" class:active={value3 === i}>
						<p>{@html text}</p>
					</div>
				{/each}
			</Scrolly>
		</div>
		
		<div class="right">
			<div class="right-inner">
				<div class="flourish-wrapper">
					<iframe src='https://flo.uri.sh/visualisation/22985770/embed' title='Interactive or visual content' class='flourish-embed-iframe' frameborder='0' scrolling='no' style='width:100%;height:600px;' sandbox='allow-same-origin allow-forms allow-scripts allow-downloads allow-popups allow-popups-to-escape-sandbox allow-top-navigation-by-user-activation'></iframe><div style='width:100%!;margin-top:4px!important;text-align:right!important;'><a class='flourish-credit' href='https://public.flourish.studio/visualisation/22985770/?utm_source=embed&utm_campaign=visualisation/22985770' target='_top' style='text-decoration:none!important'><img alt='Made with Flourish' src='https://public.flourish.studio/resources/made_with_flourish.svg' style='width:105px!important;height:16px!important;border:none!important;margin:0!important;'> </a></div>
				</div>
			</div>
	</section>

	<!-- Women time spent with partner -->
	<section>
		<div class="left">
			<Scrolly bind:value={value8}>
				{#each paragraphs8 as text, i}
					<div class="step" class:active={value3 === i}>
						<p>{text}</p>
					</div>
				{/each}
			</Scrolly>
		</div>
		
		<div class="right">
			<div class="right-inner">
				<div class="flourish-wrapper">
					<iframe src='https://flo.uri.sh/visualisation/22941354/embed' title='Interactive or visual content' class='flourish-embed-iframe' frameborder='0' scrolling='no' style='width:100%;height:600px;' sandbox='allow-same-origin allow-forms allow-scripts allow-downloads allow-popups allow-popups-to-escape-sandbox allow-top-navigation-by-user-activation'></iframe><div style='width:100%!;margin-top:4px!important;text-align:right!important;'><a class='flourish-credit' href='https://public.flourish.studio/visualisation/22941354/?utm_source=embed&utm_campaign=visualisation/22941354' target='_top' style='text-decoration:none!important'><img alt='Made with Flourish' src='https://public.flourish.studio/resources/made_with_flourish.svg' style='width:105px!important;height:16px!important;border:none!important;margin:0!important;'> </a></div>				</div>
			</div>
		</div>
	</section>


	<!-- After scrollytelling -->

	<div class="text">
		<p>The average life expectancy of women in the U.S. is 80.2 years, while for men it's only 74.8 years. So, in a heterosexual relationship where both partners are the same age and get married in middle age (let’s say around 40), the woman will, on average, live about 5.4 years longer than her partner. So, if they both reach their 40s and stay healthy into older age, she is likely to outlive him by over 5 years</p>
		<!-- Life expectancy graphic -->
		<iframe title="Life Expectancy at Birth, by sex: 2022" aria-label="Multiple Columns" id="datawrapper-chart-ABGmP" src="https://datawrapper.dwcdn.net/ABGmP/2/" scrolling="no" frameborder="0" class="datawrapper-graphic" height="249" data-external="1"></iframe><script type="text/javascript">!function(){"use strict";window.addEventListener("message",(function(a){if(void 0!==a.data["datawrapper-height"]){var e=document.querySelectorAll("iframe");for(var t in a.data["datawrapper-height"])for(var r,i=0;r=e[i];i++)if(r.contentWindow===a.source){var d=a.data["datawrapper-height"][t]+"px";r.style.height=d}}}))}();
			</script>
	</div>
	<div class="text">
		<h3>So what if men and women get remarried?</h3>
		<!-- Remarriage rates graph -->
		<iframe title="Remarriage Rates by Age Groups, 2022" aria-label="Grouped Bars" id="datawrapper-chart-CalMq" src="https://datawrapper.dwcdn.net/CalMq/2/" scrolling="no" frameborder="0" class="datawrapper-graphic" height="463" data-external="1"></iframe><script type="text/javascript">!function(){"use strict";window.addEventListener("message",(function(a){if(void 0!==a.data["datawrapper-height"]){var e=document.querySelectorAll("iframe");for(var t in a.data["datawrapper-height"])for(var r,i=0;r=e[i];i++)if(r.contentWindow===a.source){var d=a.data["datawrapper-height"][t]+"px";r.style.height=d}}}))}();
		</script>
		<p>The average remarriage rate of women after 55 years of age is 1.13 times less likely than men. That means for every 113 men that get remarried, only 100 women do on average.</p>
		<p>For a population of 169.6 million women that is just a lot of alone time!</p>
		<p>Salzinger explains that most women usually marry men older than them, and men usually marry women younger than them, so it is more unlikely that women remarry once older than men.</p>	
	</div>

	<div class="text">
		<h3>We still live in a world of gender stereotypes</h3>
		<p>Data is often a representation of reality. And while our world may have come a long way in gender equality, gender roles still have a long way to go. The data we explored today shows that traditional roles like caretaking are still a burden on young women and the bulk of breadearning on young men. But so are issues of ageism that differ by gender, the types of work men do versus women do, and more.</p>
		<p>“My own work is more qualitative, so I don't usually work with quantitative data, but I'm always fascinated by what it shows, and you do just see the traces of the sort of structural patterns of gendered life and how much things have not changed as much as you would think they might have,” said Salzinger.</p>
	</div>

	<div class="text">
		<h3>Voices Behind the Numbers: How Do People Spend Time in Daily Lives?</h3>
		<!-- First Profile -->
		<div class="container-row">
			<!-- Left column: profile image and audio player -->
			<div class="media-column">
			<img src="assets/annie-loop.gif" alt="Annie Chang" class="profile-img" />
			<audio controls class="audio">
				<source src="assets/annie-intv.m4a" type="audio/mpeg" />
			</audio>
			</div>
		
			<!-- Right column: text content -->
			<div class="text-column">
				<h3>Annie Chang</h3>
				<p>At 41, Annie Chang looks back on a life shaped by the structure and drive of a disciplined, work-focused household. She describes herself as a late bloomer who spent her twenties learning and evolving while following in her sister’s footsteps. It was not until her early thirties that she began Annie who currently lives in Berkeley now spends her time working 40 hours a week while she spends around 30 hours with her family. But this was not always the case. 			</p>
				<p>According to her, she used to work 40-60 hours a week on average during her twenties and thirties. Over time, she embraced solitude and personal growth, finding balance through meditation, volunteering, and time with her close-knit family and community. While she once envisioned a more traditional path, her experiences shaped a life centered on independence, self-reflection, and meaningful connection. Looking ahead, she imagines a peaceful future surrounded by nature, possibly working with animals or giving back through therapeutic and volunteer work.			</p>
				<p>“But I think I realized like over time that yes, like in my thirties, I was increasingly spending more and more time alone you know, just by choice or by default. But that’s also been a comfort of being alone. I just feel like there is a lot of independence to that, so I prefer that”, she said.			</p>
			</div>
		</div>

		<!-- Second Profile -->
		<div class="container-row">
			<!-- Left column: profile image and audio player -->
			<div class="media-column">
				<img src="assets/shirley-loop.gif" alt="Shirley Streshinsky" class="profile-img" />
				<audio controls class="audio">
					<source src="assets/shirley-intv.m4a" type="audio/mpeg" />
				</audio>
			</div>
		
			<!-- Right column: text content -->
			<div class="text-column">
				<h3>Shirley Streshinsky</h3>
				<p>Shirley Streshinsky, a 90-year-old  journalist, writer and widow, used to spend most of her time alone at her house in Kensington until recently as she took a fall and broke her arm. She graduated in 1956 with a journalism degree from University of Illinois, choosing the field as a practical way to make a living through writing. In her early 20s, she worked reporting jobs in Boston and Chicago and establishing herself in her career.</p>
				<p>“And although I was married I didn’t plan to have children right away. It was somewhere in the future but in fact because of that I think I got a divorce from a very nice person,” she said.</p>
				<p>After returning to Chicago, she married and later divorced her first husband. By 1966, at age 30, she moved to New York with her second husband and photojournalist Ted Streshinsky, whom she married that year. Together, they built careers as freelancers—Shirley writing for national magazines and Ted covering international photo assignments. She became a mother at 32, with the birth of her son Mark in 1967, followed by her daughter Maria in 1969.</p>
				<p>Throughout her 30s and 40s, she balanced her work as a writer with raising her children. She and Ted managed their schedules so one parent was always home, especially in the early years. As her children grew older, she shifted into travel journalism in her late 40s and 50s, writing for outlets like The San Francisco Chronicle, Los Angeles Times and others. This allowed her to travel widely while continuing her professional writing career.</p>
				<p>Throughout her 30s and 40s, she balanced her work as a writer with raising her children. She and Ted managed their schedules so one parent was always home, especially in the early years. As her children grew older, she shifted into travel journalism in her late 40s and 50s, writing for outlets like The San Francisco Chronicle, Los Angeles Times and others. This allowed her to travel widely while continuing her professional writing career.</p>
				<p>In her 60s, she started spending more time writing personal essays, and after Ted’s death in 2003 at age 80, she continued living alone in her home. Now in her late 80s, Shirley has reduced her professional work due to health challenges, including a stroke and fall, but she remains creatively active.</p>
			</div>
		</div>
	</div>
</div>
<Footer />
