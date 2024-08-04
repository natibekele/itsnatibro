<script type="text/javascript">
	import { fade, scale, fly } from 'svelte/transition';
</script>

<main class="h-full">
	<div class="experiment-grid">
		<a class="experiment-card" href="experiments/shader001">
			<h2 class="card-title">/Shader001</h2>
			<p class="experiment-card__description"></p>
			<div class="preview-image card1" />
		</a>
		<a class="experiment-card" href="experiments/shader002">
			<h2 class="card-title">/Shader002</h2>
			<p class="experiment-card__description"></p>
			<div class="preview-image card2" />
		</a>
		<a class="experiment-card" href="experiments/shader003">
			<h2 class="card-title">/Shader003</h2>
			<p class="experiment-card__description"></p>
			<div class="preview-image card3" />
		</a>
	</div>
</main>

<style>
	.h-full {
		height: 100%;
	}
	.experiment-grid {
		display: flex;
		font-family: 'Manrope';
		opacity: 1;
		margin-top: var(--small);
		flex-wrap: wrap;
		margin: 0 2rem;
	}
	.experiment-card {
		flex: 1;
		min-width: 50%;
		min-height: 40rem;
		grid-column: 1 / 2;
		border: solid 0px var(--primary);
		padding: var(--medium);
		transition: ease-in-out 0.2s;
		text-decoration: none;
		position: relative;
		overflow: hidden;
	}
	.experiment-card:hover .preview-image {
		transform: translateX(-100%);
	}
	.preview-image {
		position: absolute;
		top: 0;
		left: 100%;
		height: 100%;
		width: 100%;
		background-size: cover;
		background-repeat: no-repeat;
		transition: all ease-in-out 0.5s;
		z-index: 0;
		background-color: var(--primary);
	}
	.card1 {
		background-image: url('/images/shader001.png');
	}
	.card2 {
		background-image: url('/images/shader002.png');
	}
	.card3 {
		background-image: url('/images/shader003.png');
	}
	.experiment-card:nth-child(odd) {
		border-width: 0 0px 2px 0px;
	}
	.experiment-card:nth-child(even) {
		border-width: 0 0px 2px 0px;
	}
	.card-title {
		letter-spacing: -0.6px;
		font-size: var(--text-reg);
		font-weight: 500;
		color: var(--primary);
		/* mix-blend-mode: difference; */
		z-index: 1;
	}
</style>
