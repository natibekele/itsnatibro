<script>
	import { Canvas } from '@threlte/core';
	import { World } from '@threlte/rapier';
	import { HTML } from '@threlte/extras';
	import { T } from '@threlte/core';
	// import shader
	let fragmentShader = `
#ifdef GL_ES
precision mediump float;
#endif

uniform vec2 u_resolution;
uniform vec2 u_mouse;
uniform float u_time;

void main() {
    vec2 st = gl_FragCoord.xy/vec2(700.0, 800.0);
 	gl_FragColor = vec4(step(0.5,st.x),step(0.3, st.y),0.5,1.0);
  }`;
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
								fragmentShader: fragmentShader
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
			autocorrect="off"
			readonly
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
