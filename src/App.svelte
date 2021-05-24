<script>
	import { beforeUpdate } from 'svelte'
	import katex from 'katex'
	import '../node_modules/katex/dist/katex.css'

	let katexRaw = ''
	let renderedKatex

	beforeUpdate(() => {
		let katexString = katex.renderToString(katexRaw, {
			output: 'html',
			throwOnError: false,
		})
		renderedKatex = katexString
	})
</script>

<main>
	<textarea bind:value={katexRaw} class="font-mono"></textarea>
	<div bind:innerHTML={renderedKatex} contenteditable></div>
</main>

<style global lang="postcss">
	@tailwind base;
	@tailwind components;
	@tailwind utilities;
</style>