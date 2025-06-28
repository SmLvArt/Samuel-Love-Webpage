<script>
	import { base } from '$app/paths';
</script>

<header class="sticky top-0 z-50 w-full bg-stone-950 text-white">
	<div class="max-w-6xl mx-auto px-6 py-4">
		<nav class="flex justify-between items-center">
			<!-- Left side - Era text -->
			<div class="font-light italic scaling-text-large">
				<span>Circa 1436 BCE</span>
			</div>
			
			<!-- Right side - Navigation links -->
			<div class="flex space-x-2 sm:space-x-4 md:space-x-6 lg:space-x-8">
				<a href="{base}/" class="nav-link scaling-text">
					Home
				</a>
				<a href="{base}/gallery" class="nav-link scaling-text">
					Gallery
				</a>
				<a href="{base}/artist-statement" class="nav-link scaling-text">
					Artist Statement
				</a>
			</div>
		</nav>
	</div>
</header>
