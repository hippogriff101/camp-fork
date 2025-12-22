<script lang="ts">
	let { children } = $props();
</script>

<svelte:head>
	<title>Rooted - Hack Club at BornHack 2026</title>
	<meta name="description" content="Join Hack Club at BornHack 2026 - a week-long hacker camp in Denmark. RSVP now to secure your spot!" />
	<meta name="theme-color" content="#0a1f0a" />
	
	<!-- Open Graph -->
	<meta property="og:title" content="Rooted - Hack Club at BornHack 2026" />
	<meta property="og:description" content="Join Hack Club at BornHack 2026 - a week-long hacker camp in Denmark." />
	<meta property="og:type" content="website" />
	<meta property="og:image" content="https://hc-cdn.hel1.your-objectstorage.com/s/v3/e0523abde0f81d46_image.png" />
	
	<!-- Twitter -->
	<meta name="twitter:card" content="summary_large_image" />
	<meta name="twitter:title" content="Rooted - Hack Club at BornHack 2026" />
	<meta name="twitter:description" content="Join Hack Club at BornHack 2026 - a week-long hacker camp in Denmark." />
	
	<link rel="icon" href="https://hc-cdn.hel1.your-objectstorage.com/s/v3/e0523abde0f81d46_image.png" />
</svelte:head>

{@render children()}
