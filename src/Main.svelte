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

<svelte:head>
	<title>KaTeX Live Preview</title>
</svelte:head>

<div class="bg-blue-100 m-4 p-4 rounded-2xl">
	<label class="border-b-4 border-blue-400 font-bold mb-2 ml-4 text-lg w-max" for="katexRawElem">数式</label>
	<div class="mb-4 mt-4 pl-4 pr-4">
		<textarea bind:value={katexRaw} class="border-0 font-mono p-4 rounded-2xl w-full" placeholder="ここに数式を入力してみよう！ (例: \frac{'{'}1{'}'}{'{'}2{'}'})" id="katexRawElem" rows="5"></textarea>
	</div>
	<span class="border-b-4 border-green-400 font-bold mb-2 ml-4 text-lg w-max">出力</span>
	{#if katexRaw !== ''}
		<div bind:innerHTML={renderedKatex} class="bg-white m-4 p-4 rounded-2xl" contenteditable></div>
	{:else}
	<div class="bg-white m-4 p-4 rounded-2xl text-gray-400">まだ数式が入力されていません…</div>
	{/if}
</div>

<style global lang="postcss">
	@tailwind base;
	@tailwind components;
	@tailwind utilities;
</style>