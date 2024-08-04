<script>
	import { onMount } from 'svelte';
	import { Canvas } from '@threlte/core';
	import { World } from '@threlte/rapier';
	import { HTML } from '@threlte/extras';
	import { T, useTask } from '@threlte/core';
	import { Clock } from 'three';
	import { derived, writable } from 'svelte/store';
	// import shader
	let fragmentShader = `
#ifdef GL_ES
precision mediump float;
#endif

uniform vec2 u_resolution;
uniform vec2 u_mouse;
uniform float uTime;

vec3 colorA = vec3(0.149, 0.141, 0.456);
vec3 colorB = vec3(0.15, 0.74, 0.594);

void main() {
    vec3 color = vec3(0.0);

    float pct = abs(sin(uTime) + cos(uTime/2.0));
    color = mix(colorA, colorB, pct);
    gl_FragColor = vec4(color, 1.0);
  }`;
	let uTime = writable(0);
	let clock = new Clock();

	const shaderUniforms = derived(uTime, ($uTime) => ({
		uTime: { value: $uTime }
	}));

	const tick = () => {
		const elapsedTime = clock.getElapsedTime();
		uTime.update(() => elapsedTime);
		requestAnimationFrame(tick);
	};

	onMount(() => {
		clock.start();
		tick();
	});
</script>

<main>
	<div id="stage">
		<Canvas>
			<World>
				<T.Mesh>
					<T.PlaneGeometry args={[8, 8]} />
					<T.ShaderMaterial
						args={[
							{
								fragmentShader: fragmentShader,
								uniforms: $shaderUniforms
							}
						]}
					/>
				</T.Mesh>
				<HTML slot="fallback" transform>
					<p>
						It seems your browser<br />
						doesn't support WASM.<br />
						I'm sorry.
					</p>
				</HTML>
			</World>
		</Canvas>
	</div>

	<div class="editor">
		<textarea
			autocomplete="off"
			readonly
			autocorrect="off"
			autocapitalize="off"
			spellcheck="false"
			class="editor__input"
			bind:value={fragmentShader}
		/>
	</div>
</main>

<style>
	main {
		display: flex;
		flex-direction: row;
		padding: var(--medium);
	}
	#stage {
		flex: 1;
		max-width: 50%;
		min-height: 50rem;
		height: 100%;
	}
	.editor {
		flex: 1;
		min-height: 50rem;
		height: 100%;
		border: solid 1px;
		padding-left: var(--medium);
		padding-right: var(--medium);
	}
	.editor__input {
		background: transparent;
		border: none;
		min-height: 50rem;
		height: 100%;
		width: 100%;
		min-width: 100%;
		resize: none;
		outline: none;
	}
</style>
