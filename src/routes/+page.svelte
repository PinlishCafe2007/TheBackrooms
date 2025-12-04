<script>
	// import css
	import '$lib/styles/global.css';
	import '$lib/styles/animation.css';

	// import sections
	import Intro from '$lib/components/sections/Intro.svelte';
	import Benefits from '$lib/components/sections/Benefits.svelte';
	import Cases from '$lib/components/sections/Cases.svelte';
	import Work from '$lib/components/sections/Work.svelte';
	import Feedback from '$lib/components/sections/Feedback.svelte';
	import Action from '$lib/components/sections/Action.svelte';

</script>

<main> 
	<!-- Intro Section -->
	<Intro></Intro>

	<!-- Benefits Section -->
	<Benefits></Benefits>

	<!-- Cases Section -->
	<Cases></Cases>

	<!-- Work Process -->
	<Work></Work>

	<!-- Feedback Section -->
	<Feedback></Feedback>

	<!-- Action -->
	<Action></Action>
</main>
