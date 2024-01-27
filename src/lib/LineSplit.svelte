<script>
	import {fly, fade} from "svelte/transition"
	import { quintOut } from 'svelte/easing';
	import anime from "animejs"
	import { onMount } from "svelte"
	import IntersectionObserver from "svelte-intersection-observer";
	export let text;
	export let id;
	let observer;
	let element;
	let intersecting;
	let _container;

	const maskStyle = `overflow: hidden; display: block;position: relative;`;
	const lineStyle =`top: 0px;display: inline-block;font-size: 1.8rem;font-weight: normal;letter-spacing: 1.5;transform: translateY(100%); opacity:0;`;
	const open = `<span class="mask" style="${maskStyle}"><span class="line" style="${lineStyle}">`;
	const close = `</span></span>`

	onMount(async _ => {
		// animate = true;
		await lineSplit();
	})
	const lineSplit = async () => {
		_container = await document.getElementById(`${id}`);
		let words = await _container.querySelectorAll('.mask');
		let top = _container.offsetTop;
		const returnedLines = await parse(words, top);
		const finalText = returnedLines.join('').trim('')
		_container.innerHTML = finalText;
	}
	const parse = async (words, top) => {
		let lines = [];
		let line = open;
		const cleanText = (_text) => {
			_text = _text.replace(/&amp;/g, '&');
			_text = _text.replace(/&nbsp;/g, ' ');
			_text = _text.replace(/<br><br>/g, '<br>');
			return _text;
		}
		if (words.length === 1) {
			return [open + cleanText(words[0].innerText) + close];
		}
		return new Promise((resolve, reject) => {
			for(var x = 0; x < words.length; x++) {
				const word = words[x];
				if(word.offsetTop !== top) {
					// keep adding to same line
					line += close;
					lines.push(line);
					line = open;
					top = word.offsetTop;
				} else if(x == words.length - 1) {
					line += close;
					lines.push(line);
					resolve(lines);
					return;
				}
				let text = word.innerText;
				line += cleanText(text);
			}

			resolve(lines)
		});
	}

	const animateInText = () => {
		const elements = _container.querySelectorAll('.line');
		anime({
			targets: elements,
			translateY: 0,
			opacity: 1,
			delay: 200,
			duration: 1250,
			easing: 'easeInOutQuad'
		})
	}



</script>


<IntersectionObserver once {element} bind:intersecting threshold={0.2}
on:observe={(e) => {
	if (e.detail.isIntersecting) {
		animateInText();
	}
}}>
	<div class="container-linesplit" id={id} bind:this={element}>
		{#if text.includes(' ')}}
			{#each text.split(' ') as word, i}
			 <!-- {#if animate} -->
				<span class="mask">
					<span class="word">
						{word}&nbsp;
					</span>
				</span>
				<!-- {/if} -->
			{/each}
			{:else} 
			<span class="mask">
				<span class="word">
					{text}
				</span>
			</span>
		{/if}
	</div>
</IntersectionObserver>

<style>
	.container-linesplit {
		display: flex;
		flex-wrap: wrap;
		width: 100%;
		margin-bottom: 1rem;
	}
	.mask {
		overflow: hidden;
		display: block;
		position: relative;
	}

	.word, .line {
		top: 0px;
		display: inline-block;
		font-size: 1.6rem;
		font-weight: normal;
		letter-spacing: 1.5;
		transform: translateY(100%);
	}
</style>


