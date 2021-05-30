<script>
	import { location } from "svelte-spa-router";
</script>

<ul class="bg-gray-600 flex m-4 mb-0 rounded-t-2xl">
	<li class="ml-auto mr-4">
		{#if $location !== "/help"}
			<a
				class="hover:bg-gray-500 hover:no-underline inline-block p-4 text-gray-100 text-lg visited:text-gray-100"
				href="/#/help">ヘルプ</a
			>
		{:else}
			<a
				class="hover:bg-gray-500 bg-gray-700 hover:no-underline inline-block p-4 text-gray-100 text-lg visited:text-gray-100"
				href="/#/">ヘルプ</a
			>
		{/if}
	</li>
</ul>
