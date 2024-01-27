<script>
	import anime from "animejs"
	let mobileExpanded = false;


	function toggleMobileShow() {
		mobileExpanded = !mobileExpanded;

		if(mobileExpanded) {
			anime.timeline({
			easing: 'easeInOutSine',
			autoplay: true,
			duration: 500
			})
			.add({
				targets: '.mobile-links',
				translateX: '-100%',
				easing: 'easeInOutSine',
			})
			.add({
				targets: ['.bar-1', '.bar-3'],
				opacity: 0
			}, 100)
			.add({
				targets: '.bar-2',
				rotateZ: '45deg',
			}, 250)
			.add({
				targets: '.bar-4',
				translateX: '-50%',
				translateY: '-50%',
				rotateZ: '-45deg',
				opacity: 1,
			}, 250);
			return
		}
		anime.timeline({
			easing: 'easeInOutSine',
			duration: 500,
			autoplay: true,
			})
			.add({
				targets: '.mobile-links',
				translateX: '0%',
				easing: 'easeInOutSine'
			},100)
			.add({
				targets: ['.bar-1', '.bar-3'],
				opacity: 1
			}, 400)
			.add({
				targets: '.bar-2',
				rotateZ: '0deg', 
			},200)
			.add({
				targets: '.bar-4',
				rotateZ: '0deg', 
				opacity: 0
			},200);

	}
</script>
<nav class="header">
	<ul class="header--ul">
		<li class="header--big-text"> NATHAN SHANKO </li>

		<li class="header--link"><a href="/">/ home</a><span class="block"></span></li>
		<li class="header--link"><a href="/projects">/ prjcts</a><span class="block"></span></li>
		<li class="header--link"><a href="/experiments">/ exprmnts</a><span class="block"></span></li>


		<!-- <li class="header--link"><a href="/">/ cming suːn</a><span class="block"></span></li> -->
	</ul>

	<div class="mobile-nav" on:click={toggleMobileShow}>
		<div class="bar bar-1"></div>
		<div class="bar bar-2"></div>
		<div class="bar bar-3"></div>
		<div class="bar bar-4"></div>

		<ul class="mobile-links">
			<li class="mobile-links__link"><a href="/">/ home</a></li>
			<li class="mobile-links__link"><a href="/projects">/ prjcts</a></li>
			<li class="mobile-links__link"><a href="/experiments">/ exprmnts</a></li>
		</ul>
	</div>

	<div class="border-bottom"></div>
</nav>


<style>
	.header {
		width: calc(100% - 4rem);
		font-family: 'Manrope';
		background: var(--base);
		padding: 0.4rem 0;
		position: fixed;
		transform: translateX(2rem);
		display: grid;
		z-index: 10;
	}
	.header--ul {
		padding: 0.5rem 1rem;
		list-style: none;
		display: flex;
		align-items: center;
	}
	.header--big-text {
		font-size: 2.2rem;
		font-weight: 700;
		letter-spacing: -1.92px;
		line-height: 110%;
		pointer-events: none;
		margin-right: 9rem;
		text-transform: lo;
	}
	.header--link {
		font-size: 1.5rem;
		font-weight: 400;
		margin-right: 9rem;
		letter-spacing: -0.5px;
		overflow: hidden;
		height: 100%;
		transition: ease-out 0.2s;
		padding: 0.5rem 1rem;
		position: relative;
		z-index: 1;
		color: var(--black);
/*		mix-blend-mode: color-burn;*/
	}
	.header--link:hover > a {
/*		color: var(--white);*/
/*		font-weight: bold;*/
	}
	.header--link > a {
		z-index: 1;
	}
	.header--link:hover > .block {
		transform: translateX(100%);
	}


	.block {
		position: absolute;
		background: var(--accent);
		height: 100%;
		width: 100%;
		left: -100%;
		top: 0%;
		color: var(--primary);
		transition: ease-out 0.3s;
		z-index: -1;
	}

	a {
		text-decoration: none;
		color: inherit;
	}

	.mobile-nav {
		display: none;
		flex-direction: column;
		gap: 0.5rem;
		position: absolute;
		top: 1.4rem;
		right: 2rem;
	}

	.mobile-links {
		position: fixed;
		height: 101vh;
		width: 100vw;
		background: var(--primary);
		top: 0;
		left: calc(100% + 2rem);
		padding: 2rem;
		list-style: none;
		margin: 0;
	}

	.mobile-links__link {
		font-size: 4rem;
		line-height: 1.5;
		color: var(--white);
		font-weight: medium;
		margin-bottom: 5rem;
	}

	.bar {
		display: inline-block;
		height: 0.5rem;
		width: 4rem;
		background: var(--white);
		z-index: 9;
		mix-blend-mode: difference;
	}
	.bar-4 {
		position: absolute;
		top: 50%;
		left: 50%;
		transform: translate(-50%,-50%);
		opacity: 0;
	}
	.bar2, .bar4 {
		transform-origin: center;
	}

	.border-bottom {
		position: absolute;
		bottom: 1px;
		height: 2px;
		width: 100%;
		background: var(--primary);
	}

	@media(max-width: 1200px){
		.header--big-text {
			margin-right: 6rem;
		}

		.header--link {
			margin-right: 2rem;
		}
	}

	@media(max-width: 800px) {
		.mobile-nav {
			display: flex;
		}
		.header--link {
			display: none;
		}
		.border-bottom {
/*			display: none;*/
		}
	}

</style>