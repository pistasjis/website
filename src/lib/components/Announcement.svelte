<script lang="ts">
	import dayjs from "dayjs";

	export let data: any;
</script>

{#if data}
	{#if !data.error}
		{#if data.incident}
			<div
				class="flex flex-col items-left justify-left gap-2 announcement mt-5 p-4 bg-fourthbackground max-w-xl w-full rounded-md"
			>
				<div class="flex flex-row items-center justify-left gap-2">
					{#if data.incident.style === "info"}
						<div class="i-tabler-info-circle text-2xl" />
					{/if}
					{#if data.incident.style === "warning"}
						<div class="i-tabler-alert-triangle text-2xl" />
					{/if}
					{#if data.incident.style === "danger"}
						<div class="i-tabler-alert-circle text-2xl" />
					{/if}
					{#if data.incident.style === "primary"}
						<div class="i-tabler-circle-check text-2xl" />
					{/if}
					<h2 class="text-2xl">{data.incident.title}</h2>
				</div>
				<!-- For some reason the html escapes announcement-content when you're not using JavaScript and creates a really weird animation where you can see the padding be reduced on initial load. This fixes it, I think. -->
				<div class="incident-container">
					<p class="break-all max-w-max announcement-content">
						<!-- Using @html is unsafe, but we have already sanitized the content beforehand so it's OK. -->
						{@html data.incident.content}
					</p>
				</div>
				<p>
					Created at {dayjs(data.incident.createdDate).format(
						"ddd, DD MMM YYYY HH:mm"
					)}
				</p>
			</div>
		{/if}
	{/if}
{/if}

{#if data.incident}
	<style>
		.announcement-content > p > a {
			color: white;
			text-decoration: underline;
			text-underline-offset: 0.25rem;
			transition: all 0.2s ease-in-out;
		}

		.announcement-content > p > a:hover {
			text-decoration-color: var(--accent);
		}
	</style>
	{#if data.incident.style === "info"}
		<style>
			.announcement {
				border-bottom: 3px solid #0dcaf0;
			}
		</style>
	{/if}
	{#if data.incident.style === "warning"}
		<style>
			.announcement {
				border-bottom: 3px solid #f8a306;
			}
		</style>
	{/if}
	{#if data.incident.style === "danger"}
		<style>
			.announcement {
				border-bottom: 3px solid #dc3545;
			}
		</style>
	{/if}
	{#if data.incident.style === "primary"}
		<style>
			.announcement {
				border-bottom: 3px solid #199964;
			}
		</style>
	{/if}
{/if}
