<script type="text/javascript">
	import { fade, scale, fly } from "svelte/transition";
	import AnimatedText from "$lib/AnimatedText.svelte"
	import RotatingSphere from "$lib/RotatingSphere.svelte"
	import WordSplit from "$lib/WordSplit.svelte"
	import { quintOut } from 'svelte/easing';
</script>

<div class="container" in:fade={{ duration: 500 }} out:fade={{duration: 500}}>
	<!-- <AnimatedText text={"Lorem ipsum"} /> -->
	<!-- <RotatingSphere /> -->
		<div class="block">
		<div class="child">
			<img src="images/nostalgiabox2.jpg" alt="just football project laptop mockup"
				class="project-image"
				transition:fade={{ duration: 500 }} />
		</div>
		<div class="child">
			<div class="text-container">
				<h3 > NostalgiaBox </h3>
				<h3 class="accent"> 2023 </h3>
			</div>
		</div>
	</div>
	<div class="block">
		<div class="child">
			<div class="text-container">
				<p class="proj-description">
					At NostalgiaBox, we believe in the profound power of memories. Our ethos is rooted in the idea that life's most meaningful moments are too precious to be lost in the whirlwind of time. Our purpose is to provide a sanctuary where these moments can be preserved, cherished, and rediscovered.
					<br />
					<br />

					NostalgiaBox is a React Native application that targets iOS/Android platforms and implements a unique approach in capturing and storing memories.
					<br />
					<br />
					Creating captivating narratives in a timeless way that reminds us that we should make memories while we can, and the first person we should be looking to plese is ourselves, not the world!
					<br />
					<br />

					<a target="blank" href="https://nostalgiabox.app" class="site-link">Live Link.</a>
				</p>
			</div>
		</div>
		<div class="child">
			<img src="images/nostalgiabox1.jpg" alt="justfootball project desktop mockup" class="project-image"
				transition:fade={{ duration: 500 }}/>
		</div>
	</div>
	<div class="block">
		<div class="child">
			<img src="images/justfootball.jpg" alt="just football project laptop mockup" class="project-image"
				transition:fade={{ duration: 500 }}/>
		</div>
		<div class="child">
			<div class="text-container">
				<h3> Football -- Village </h3>
				<h3 class="accent"> 2023 </h3>
			</div>
		</div>
	</div>
	<div class="block">
		<div class="child">
			<div class="text-container">
				<p class="proj-description">
					Football--Village is a dynamic project designed to cultivate continuous learning and elevate football analysis and coaching skills. As a dedicated platform, it serves as a centralized hub for a diverse range of football-related work.
					<br />

					Weekly, the site unveils articles that delve into various coaching topics, encompassing game analysis, contemporary football trends, session planning, exercises, management insights, and compelling data analysis or visualizations.
					<br />

					At its core, Football--Village aims to be a learning sanctuary for aspiring coaches, football enthusiasts, and players eager to deepen their understanding and enjoyment of the sport. The commitment to delivering substantial content is a personal journey to grow and gain a profound appreciation for the intricacies of the game.
					<br />

					This project seeks to foster a community where growth is a shared experience, nurturing relationships that benefit everyone involved. It stands out by offering youth coaching resources freely, recognizing that coaching extends beyond individuals—it's about the holistic development of players. By supporting coaches in their roles, the project strives to cultivate not only superior players but better individuals.
					<br />

					Step into this space, where football enthusiasts discover valuable resources and contribute to an ever-evolving journey in football development.

					<br />
					<br />
					<a target="blank" href="https://just-football.vercel.app" class="site-link">Live Link.</a>
				</p>
			</div>
		</div>
		<div class="child">
			<img src="images/justfootball2.jpg" alt="justfootball project desktop mockup" class="project-image"
				transition:fade={{ duration: 500 }}/>
		</div>
	</div>

	<div class="block">
		<div class="child">
			<img src="images/sundance.jpg" alt="sundance project laptop mockup" class="project-image"
				transition:fade={{ duration: 500 }}/>
		</div>
		<div class="child">
			<div class="text-container">
				<h3> Sundance, New Frontier </h3>
				<h3 class="accent"> 2022 </h3>
			</div>
		</div>
	</div>
	<div class="block">
		<div class="child">
			<div class="text-container">
				<p class="proj-description">
					The New Frontier program was “a fully biodigital showcase”. A globally accessible online project from Jan. 20-28, 2022, with in-person extensions and live performances at The Craft, a new artist-centered venue in Park City. Originally birthed as a response to the coronavirus pandemic, New Frontier created a space were people could still experience the Sundance Film Festival from the comfort, and safety of their own homes. 
					<br />
					<br />
					Live premiers following an event schedule, VR immersion, real time audio and video chats in 3D enviornments, text chat, and attendee lists, all features that were built and offered in the New Frontier for Sundance.
					<br />
					<br />
					<a target="blank" href="https://www.sundance.org/blogs/2022-sundance-film-festival-new-frontier-spans-biodigital-terrain-blends-online-in-person-in-real-time/" class="site-link">Sundance Blog Post.</a>
				</p>
			</div>
		</div>
		<div class="child">
			<img src="images/sundance2.jpg" alt="sundance project laptop mockup" class="project-image"
				transition:fade={{ duration: 500 }}/>
		</div>
	</div>
</div>

<style>
	h3 {
		font-size: 2.4rem;
		letter-spacing: -0.2rem;
		margin: 0;
		font-weight: 500;
	}
	p {
		font-size: 1.6rem;
	}

	.container {
		display: grid;
		grid-template-columns: repeat(10, 1fr);
		grid-auto-rows: minmax(20rem, auto);
		font-family: 'Manrope';
		opacity: 1;
		padding: 4rem 2rem;
/*		padding-top: 8rem;*/
	}

	.block {
		grid-column: 1/11;
		display: flex;
		margin-bottom: 6rem;
	}
	.child {
		display: flex;
		justify-content: space-between;
		align-items: center;
		flex: 1;
		height: auto;
/*		overflow: hidden;*/
	}
	.text-container {
		display: flex;
		height: 100%;
		flex-direction: column;
		justify-content: space-between;
		padding: 3rem 1.5rem;
	}
	.site-link {
		color: var(--black);
		text-decoration: underline;
		font-size: 1.8rem;
	}
	.project-image {
		height: 100%;
		width: 100%;
		max-height: 72rem;
		max-width: 94rem;
		border-radius: 15%;
		object-fit: cover;
		border: solid 1px var(--primary);
		aspect-ratio: 4/5;
		margin: auto;
	}
	.proj-description {
		font-size: 1.8rem;
		font-weight: normal;
		letter-spacing: 1.2%;
		line-height: 1.5;
	}

	.accent {
		/*background: var(--primary);
		color: var(--accent);*/
	}

	@media(max-width: 800px) {
		.mgrid {
			display: flex;
			flex-direction: column;
		}
		.block {
			flex-direction: column;
		}
		.child {
		}
	}
</style>