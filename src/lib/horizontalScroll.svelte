<script>
	import { onMount } from "svelte"
	let images = [];
	let clientWidth;
	let reachedEnd = false

	onMount(() => {
	  let scrollSpeed = 10;
	  let scroller = document.getElementById("scroller");

	  // scroller.addEventListener("wheel", e => {
	  // 	const topBorderPos = scroller.getBoundingClientRect().y
	  // 	// console.log(topBorderPos)
	  //   if(!e.deltaY) return;
	  //   // if (Math.abs(topBorderPos) > 1) return;
	  //   let scrollDirection = (e.deltaY > 0) ? 1 : -1;
	  //   scroller.scrollLeft += (scrollSpeed * scrollDirection);
	  //   let scrollLeft = Math.round(scroller.scrollLeft);
	  //   let maxScrollLeft = Math.round(scroller.scrollWidth - scroller.clientWidth);
	    
	  //   if((scrollDirection === -1 && scrollLeft > 0) || (scrollDirection === 1 && scrollLeft < maxScrollLeft))  e.preventDefault()
	  //   return true;
	  // }, false);
	})
</script>

<div class="horizontal-container" id="scroller">

	<div class="overflow" id="scroller-2">
		<div class="img-container">
			<img src="https://images.unsplash.com/photo-1702728139631-e50607576454?q=80&w=2689&auto=format&fit=crop&ixlib=rb-4.0.3&ixid=M3wxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHx8fA%3D%3D" alt="project-image" />
		</div>
		<div class="img-container">
			<img src="https://images.unsplash.com/photo-1699341606473-3038483f93c1?q=80&w=3087&auto=format&fit=crop&ixlib=rb-4.0.3&ixid=M3wxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHx8fA%3D%3D" alt="project-image" />
		</div>
		<div class="img-container">
			<img src="https://images.unsplash.com/photo-1605827462530-3f1a7d00089f?q=80&w=2048&auto=format&fit=crop&ixlib=rb-4.0.3&ixid=M3wxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHx8fA%3D%3D" alt="project-image" />
		</div>
		<div class="img-container">
			<img src="https://images.unsplash.com/photo-1700684163033-9dc32ab600a9?q=80&w=2145&auto=format&fit=crop&ixlib=rb-4.0.3&ixid=M3wxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHx8fA%3D%3D" alt="project-image" />
		</div>
		<div class="ender">

		</div> 
	</div>

	<div id="scroll-window"></div>
</div>

<style>
	.horizontal-container {
		grid-column: 1/11;
		flex: 1;
		display: flex;
		flex-wrap: nowrap;
		align-items: flex-start;
/*		border-radius: 30rem;*/
/*		overflow: hidden;*/
		width: 100vw;
		margin-bottom: 10rem;
		overflow-x: scroll;
		position: relative;
/*		scroll-behavior: smooth;*/
	}
	.horizontal-container::-webkit-scrollbar {
		background: var(--base);
	}
	.horizontal-container::-webkit-scrollbar-thumb {
		display: none;
	}
	.horizontal-container::-webkit-scrollbar-track {
		display:  none;
	}
	.overflow {
		display: inline-flex;
	}
	.ender {
		width: 100vw;
		height: 99vh;
		flex-grow: 1;
		align-items: flex-start;
/*		flex: 1;*/
	}

	.img-container {
		width: 50vw;
		height: 99vh;
/*		display: inline-block;*/
		flex-grow: 1;
		align-items: flex-start;
/*		flex: 2;*/
	}
	.img-container > img {
		height: 100%;
		width: 100%;
		object-fit: cover;
	}

	#scroll-window {
		height: 100%;
		width: 50%;
		position: absolute;
		top: 0;
		left: 0;
	}
</style>