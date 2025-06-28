<script lang="ts">
	export let imagePath: string;
	export let caption: string;
	export let aspectRatio: number;
</script>

<figure class="w-full h-full bg-transparent rounded flex flex-col" style="aspect-ratio: {aspectRatio}">
	<img src={imagePath} alt={caption} class="w-full object-contain rounded-t bg-transparent" />
	<figcaption class="p-2 text-center text-sm text-stone-300 bg-transparent rounded-b">
		{caption}
	</figcaption>
</figure>
