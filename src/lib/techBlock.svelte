<script>
</script>


<div class="container">
	<h1 class="title">Tchnlgy</h1>

	<div class="spacer"></div>


	<div class="col1">
		<h4 class="col-title">frnt end</h4>

		<p class="tech">react</p>
		<p class="tech">svelte</p>
		<p class="tech">vue</p>
		<br />
		<p class="tech">three.js</p>
		<p class="tech">glsl</p>
		<p class="tech">webgl</p>
		<br />
		<p class="tech">sass</p>
		<p class="tech">less</p>
		<p class="tech">tailwind</p>
		
	</div>

	<div class="col2">
		<h4 class="col-title">bck end</h4>

		<p class="tech">node</p>
		<p class="tech">docker</p>
		<p class="tech">bun</p>
		<br />
		<p class="tech">express</p>
		<p class="tech">django</p>
		<p class="tech">fastapi</p>
		<br />
		<p class="tech">google cloud</p>
		<p class="tech">mondodb</p>
		<p class="tech">postgres</p>
		<p class="tech">firebase</p>

		
	</div>

	<div class="col3">
		<h4 class="col-title">ntve</h4>

		<p class="tech">iOS (Swift / SwiftUI / ObjectiveC)</p>
		<p class="tech">Android (Kotlin / Java )</p>
		<p class="tech">React Native</p>
		
	</div>

	<div class="col4">
		<h4 class="col-title">dsgn</h4>

		<p class="tech">i dabble...</p>
		<p class="tech">but better every day</p>
		<p class="tech">i did dsgn this site</p>
		
	</div>
</div>

<style>
	.container {
		grid-column: 2/10;
		grid-row: 2;
		display: grid;
		grid-template-columns: repeat(8, 1fr);
		grid-gap: 2rem;
		margin-bottom: 10rem;
		position: relative;
	}

	.title {
		text-transform: lowercase;
		font-weight: 600;
		font-size: 8rem;
		letter-spacing: -4.8px;
		margin-bottom: 5rem;
		grid-column: 1/9;
	}

	.spacer {
		width: 100%;
		height: 1px;
		background: var(--primary);
		grid-column: 1/9;
		margin-bottom: 5rem;
	}

	.col-title {
		font-size: 2.4rem;
		font-weight: 600;
		letter-spacing: -1.44px;
		margin-bottom: 2.5rem;
	}
	.tech {
		font-size: 1.6rem;
		line-height: 140%;
		letter-spacing: -0.32px;
		margin: 0;
		padding: 0;
		text-transform: lowercase;
	}

	.col1 {
		grid-column: 1/3;
	}
	.col2 {
		grid-column: 3/5;
	}
	.col3 {
		grid-column: 5/7;
	}
	.col4 {
		grid-column: 7/9;
	}
	.col1,.col2,.col3,.col4 {
/*		background: var(--accent);*/
	margin-bottom: 10rem;
	}



</style>