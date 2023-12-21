<header class="header">
	<ul class="header--ul">
		<li class="header--big-text"> NATHAN SHANKO </li>

		<li class="header--link"><a href="/">/ home</a><span class="block"></span></li>
		<li class="header--link"><a href="/">/ cming suːn</a><span class="block"></span></li>
		<li class="header--link"><a href="/">/ cming suːn</a><span class="block"></span></li>


		<li class="header--link"><a href="/">/ cming suːn</a><span class="block"></span></li>
	</ul>

	<div class="border-bottom"></div>
</header>


<style>
	.header {
		width: 100%;
		font-family: 'Manrope';
		background: var(--base);
		padding: 2.4rem 0;
		position: relative;
		margin: 0 2rem;
		display: grid;
	}
	.header--ul {
		padding: 0.5rem 1rem;
		list-style: none;
		display: flex;
		align-items: center;
	}
	.header--big-text {
		font-size: 3.2rem;
		font-weight: 700;
		letter-spacing: -1.92px;
		line-height: 110%;
		pointer-events: none;
		margin-right: 9rem;
		text-transform: lo;
	}
	.header--link {
		font-size: 1.5rem;
		font-weight: 500;
		margin-right: 9rem;
		letter-spacing: -0.5px;
		overflow: hidden;
		height: 100%;
		transition: ease-out 0.2s;
		padding: 0.5rem 1rem;
		position: relative;
		z-index: 1;
		mix-blend-mode: color-burn;
	}
	.header--link:hover > a {
		color: var(--white);
	}
	.header--link > a {
		z-index: 1;
	}
	.header--link:hover > .block {
		transform: translateX(100%);
	}


	.block {
		position: absolute;
		background: var(--primary);
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
		color: var(--black);
	}

	.border-bottom {
		position: absolute;
		bottom: 1px;
		height: 1px;
		width: 100%;
		background: var(--primary);
	}

	@media(max-width: 1200px){
		.header--big-text {
			margin-right: 6rem;
		}

		.header--link {
			margin-right: 3rem;
		}
	}

	@media(max-width: 800px) {
		.header--link {
			display: none;
		}
		.border-bottom {
			display: none;
		}
	}

</style>