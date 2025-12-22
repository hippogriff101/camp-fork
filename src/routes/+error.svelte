<script>
    import { onMount } from 'svelte';
    
    let pageLoaded = $state(false);

    // Fixed number of fireflies for error page
    const fireflyCount = 50;
    
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
            <h2>Rooted - 404 Not Found</h2>
                <img class="error" src="/confused_dino-removebg.png" alt="404 image" />
            <p class="stats-link">Looks like you got a bit lost, the page you are looking for does not exist.</p>
            <br>
            <a href="/" class="rsvp-btn">Head back home!</a>

        
        <nav class="nav-buttons">
            <a href="/about" class="info-btn">What is this?</a>
        </nav>
        
        
        </div>
    </div>
{/if}
