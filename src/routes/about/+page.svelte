<script lang="ts">
	import ReadMoreButton from "$lib/components/ReadMoreButton.svelte";
	import Hero from "$lib/components/Hero.svelte";
	import Bio from "$lib/components/Bio.svelte";

	import SvelteSeo from "svelte-seo";
</script>

<svelte:head>
	<title>About | Pistasjis</title>
</svelte:head>

<SvelteSeo
	title="About | Pistasjis"
	description="About me and stuff"
	canonical="https://pistasjis.net/about"
	openGraph={{
		type: "article",
		url: `https://pistasjis.net/about`,
		title: `About | Pistasjis`,
		description: `About me and stuff`
	}}
/>

<div class="flex flex-col justify-center items-center">
	<section class="second-background">
		<Hero />
	</section>
	<div class="content">
		<Bio noReadMore />
		<div class="flex flex-col items-left gap-4 mt-5 max-w-xl">
			<h2
				class="text-2xl"
				id="donate"
			>
				Donate
			</h2>
			<p>I can accept donations in Monero or Bitcoin.</p>
			<h3
				class="text-xl"
				id="monero"
			>
				Monero
			</h3>
			<p>
				My Monero address is: <code
					class="break-all bg-fourthbackground p-0.5 rounded-md"
					>45wYu3oEAhu7s9aodftL2iBztYCdKzTZ4gaTRXGRRsN8cfVbdDMrVCEDmUczBiosE3ESVtyRKodXKgcTThyNsF2XGJvee5V</code
				>
			</p>
			<p>
				You can also put "pistasjis.net" in your Monero client if it
				supports OpenAlias.
			</p>
			<details
				title="QR code"
				class="cursor-pointer"
			>
				<summary>QR code</summary>
				<img
					src="/ha4t207b.bmp"
					alt="Monero donation QR code"
					class="mt-3 w-1/2 rounded-xl"
				/>
			</details>
			<h3
				class="text-xl"
				id="bitcoin"
			>
				Bitcoin
			</h3>
			<p>
				My Bitcoin address is: <code
					class="break-all bg-fourthbackground p-0.5 rounded-md"
					>bc1qsk2ntfzvl4zfkrfkmqp65w0q9xn9v09xvfezz7</code
				>
			</p>
			<details
				title="QR code"
				class="cursor-pointer"
			>
				<summary>QR code</summary>
				<img
					src="/bitcoin.png"
					alt="Bitcoin donation QR code"
					class="mt-3 w-1/2 rounded-xl"
				/>
			</details>
			<p class="text-xl">Thank you for your support!</p>
			<ReadMoreButton
				href="/"
				text="Want to go back home?"
			/>
		</div>
	</div>
</div>
