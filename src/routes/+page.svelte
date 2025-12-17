<script>
    import { onMount } from 'svelte';
    
    let { data } = $props();
    let pageLoaded = $state(false);

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
        
        <!-- Fireflies -->
        <div class="firefly"></div>
        <div class="firefly"></div>
        <div class="firefly"></div>
        <div class="firefly"></div>
        <div class="firefly"></div>
        <div class="firefly"></div>
        <div class="firefly"></div>
        <div class="firefly"></div>
        
        <div class="bg-content">
            <h2>Rooted</h2>
            {#if data.rsvpCount !== null}
                <p class="rsvp-count">{data.rsvpCount} already rooted</p>
            {/if}
            <a href="https://forms.hackclub.com/camprsvp" class="rsvp-btn" target="_blank" rel="noopener">RSVP</a>
            <a href="/stats" class="stats-link">View live stats →</a>
        </div>
        <div style="position: absolute; top: 30px; right: 30px; z-index: 1;">
            <a href="/about" class="info-btn">What is this?</a>
        </div>
    </div>
{/if}
