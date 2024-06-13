<script>
	import { fade, slide } from "svelte/transition";
    import Background from "../components/animatedbg_scrollingtext.svelte";
	import Text from "../components/Typewritertext.svelte";
	import Fire from "../components/burningfire.svelte";
</script>

<div class="container h-full mx-auto flex justify-center items-center flex-col p-6">
	<Background />
	<div class="md:w-4/6 mr-auto pb-20 pt-20">
		<Text />
	</div>
	<div class="fixed top-perc right-1/4">
		<Fire />
	</div>
	


	
</div>

<style>
	.top-perc {
		top: calc(35% - 7vw);
	}
</style>