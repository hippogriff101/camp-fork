<script>
    import { onMount } from 'svelte';
    
    let { data } = $props();
    let pageLoaded = $state(false);

    // Number of fireflies = RSVP count (with a reasonable max for performance)
    const fireflyCount = Math.min(data.rsvpCount ?? 0, 100);
    
    // Generate random positions and animation timings for each firefly
    const fireflies = Array.from({ length: fireflyCount }, (_, i) => ({
        id: i,
        left: Math.random() * 100,
        top: Math.random() * 100,
        floatDuration: 14 + Math.random() * 10,
        glowDuration: 2.5 + Math.random() * 1.5,
        floatDelay: -Math.random() * 15,
        glowDelay: -Math.random() * 3
    }));

    onMount(() => {
        const img = new Image();
        
        img.onload = () => {
            pageLoaded = true;
        };
        
        img.onerror = () => {
            pageLoaded = true;
        };

        img.src = '/bg.jpg';
        
        // If cached, loads instantly
        if (img.complete) {
            pageLoaded = true;
        }
    });
</script>

<svelte:head>
    <link rel="preload" href="/bg.jpg" as="image">
</svelte:head>

<style> 
    @import "./styles.css";
</style>

{#if !pageLoaded}
    <div class="loading-screen">
        <p class="progress-text">Loading...</p>
    </div>
{:else}
    <div class="bg-container">
        <div class="bg-overlay"></div>
        
        <!-- Fireflies based on RSVP count -->
        {#each fireflies as fly (fly.id)}
            <div
                class="firefly"
                style="left: {fly.left}%; top: {fly.top}%; animation-duration: {fly.floatDuration}s, {fly.glowDuration}s; animation-delay: {fly.floatDelay}s, {fly.glowDelay}s;"
            ></div>
        {/each}
        
        <div class="bg-content">
            <h2>Rooted</h2>
            {#if data.rsvpCount !== null}
                <p class="rsvp-count">{data.rsvpCount} already rooted</p>
            {/if}
            <a href="https://forms.hackclub.com/camprsvp" class="rsvp-btn" target="_blank" rel="noopener">RSVP</a>
            <a href="/stats" class="stats-link">View live stats →</a>
        <div style="position: absolute; top: 80px; left: 30px; z-index: 1;">
            <a href="https://hackclub.enterprise.slack.com/archives/C09LYU1S23Y" class="rsvp-btn" target="_blank" rel="noopener">#Rooted Slack Channel</a>
            <a href="/about#learn-more" class="about-link">Take a look at the FAQ for info on how to join Slack!</a>
        </div>
        </div>
        <div style="position: absolute; top: 30px; right: 30px; z-index: 1;">
            <a href="/about" class="info-btn">What is this?</a>
            
        </div>
        <div style="position: absolute; top: 100px; right: 30px; z-index: 1;">
            <a href="/orgs" class="info-btn">Meet the Orgs!</a>
        </div>
    </div>
{/if}
