<script lang="ts">
	import "uno.css";
	import "$lib/styles/app.css";
	import "@unocss/reset/tailwind.css";
	import Transition from "$lib/components/Transition.svelte";
	import Nav from "$lib/components/Nav.svelte";
	import Elevator from "$lib/components/Elevator.svelte";
	import Noscript from "$lib/components/Noscript.svelte";
	import LoadProgress from "$lib/components/LoadProgress.svelte";
	import type { LayoutData } from "./$types";
	import { navigating } from "$app/stores";
	let YValue = 0;
</script>

<!-- <noscript>
    <Noscript />
</noscript> -->

<Nav />

<main>
	<!--
    {#if YValue > 100}
        <Elevator />
    {/if}
    -->
	<slot />
</main>

<svelte:window bind:scrollY={YValue} />
