<script lang="ts">
	import { CodeBlock } from '@skeletonlabs/skeleton';
	let lines: string[] = [];
	let value: string = "this\n\nis\n\na\n\nsample";

	$: lines = value.split("\n\n").map((line) => line.trim()).filter((line) => line.length > 0);
</script>

<div class="container mx-auto mt-4 flex flex-col gap-y-4">
	<h1 class="h1 text-center">Xerox</h1>
	<p class="text-center">Write text into the box below. Each paragraph (separated by an empty line) will become a copyable block of text.</p>

	<div class="flex gap-x-4">
		<div class="flex-1">
			<textarea class="textarea" rows="10" cols="50" placeholder="Type here..." bind:value></textarea>
		</div>
		<div class="flex-1">
			{#each lines as line}
				<CodeBlock class="mb-4" code={line} />
			{/each}
		</div>
	</div>
</div>
