<script>
    let bornhackOpen = $state(false);
</script>

<style>
    @import "../styles.css";
</style>

<div class="about-container">
    <div class="about-content">
        <a href="/" class="back-btn">← back</a>

        <div class="wip-banner">
            <span class="icon">🚧</span>
            <span class="text">Rooted is a work-in-progress.</span>
        </div>
        
        <h1 class="title">Rooted FAQ</h1>

        <!-- BornHack Collapsible Section -->
        <div class="collapsible-section">
            <button class="collapsible-header" onclick={() => bornhackOpen = !bornhackOpen}>
                <span class="collapsible-title">🏕️ About BornHack</span>
                <span class="collapsible-arrow" class:open={bornhackOpen}>▶</span>
            </button>
            
            {#if bornhackOpen}
                <div class="collapsible-content">
                    <div class="bornhack-info">
                        <p>
                            <a href="https://bornhack.dk" target="_blank" rel="noopener">BornHack</a> is an annual week-long hacker camp held on the Danish island of Funen. You'll camp outdoors, build projects, attend talks,And so much more.
                        </p>
                        <p>
                            BornHack 2026 will likely take place in <strong>July 2026</strong> (exact dates TBD). The event runs for about a week.
                        </p>
                    </div>

                    <div class="photo-gallery">
                        <div class="gallery-grid">
                            <img src="https://hc-cdn.hel1.your-objectstorage.com/s/v3/4a2670327c6112ff_logotent_pink_people.jpg" alt="BornHack tent with people" loading="lazy" decoding="async" width="300" height="200" />
                            <img src="https://hc-cdn.hel1.your-objectstorage.com/s/v3/a526b457de420ccf_participant_tent_laptop.jpg" alt="Participant coding in tent" loading="lazy" decoding="async" width="300" height="200" />
                            <img src="https://hc-cdn.hel1.your-objectstorage.com/s/v3/b591d8f962f07947_night_stars_lights.jpg" alt="Night sky with lights" loading="lazy" decoding="async" width="300" height="200" />
                            <img src="https://hc-cdn.hel1.your-objectstorage.com/s/v3/760b56b7773483d0_dome_lights.jpg" alt="Dome with colorful lights" loading="lazy" decoding="async" width="300" height="200" />
                            <img src="https://hc-cdn.hel1.your-objectstorage.com/s/v3/bf6b2b0ca5dff899_ellen_tesla_coil.jpg" alt="Tesla coil demonstration" loading="lazy" decoding="async" width="300" height="200" />
                            <img src="https://hc-cdn.hel1.your-objectstorage.com/s/v3/c6b87a72a4e46b41_bar_people.jpg" alt="People at the bar" loading="lazy" decoding="async" width="300" height="200" />
                        </div>
                        <p class="gallery-credit">Photos from <a href="https://bornhack.dk" target="_blank" rel="noopener">bornhack.dk</a></p>
                    </div>

                    <iframe src="https://www.google.com/maps/embed?pb=!1m18!1m12!1m3!1d2266.4177307032205!2d9.936464176173745!3d55.385617020213814!2m3!1f0!2f0!3f0!3m2!1i1024!2i768!4f13.1!3m3!1m2!1s0x464cc191437ffa5b%3A0x87b7c392691fc596!2sBornHack!5e0!3m2!1sen!2sdk!4v1766092854910!5m2!1sen!2sdk" width="100%" height="250" style="border:0; border-radius: 8px;" allowfullscreen={true} loading="lazy" referrerpolicy="no-referrer-when-downgrade" title="BornHack location map"></iframe>
                </div>
            {/if}
        </div>

        <!-- General FAQs -->
        <div class="faq-item">
            <h2 class="faq-question">What is Hack Club?</h2>
            <p class="faq-answer">
                Hack Club is a global community of teenage hackers who love building and coding things. 
                We run clubs, events, and projects around the world to help teens learn, create, and connect.
            </p>
        </div>

        <div class="faq-item">
            <h2 class="faq-question">My parents are nervous about me attending. How can I reassure them?</h2>
            <p class="faq-answer">
                That's totally understandable! BornHack is a safe environment, which has been run many times. 
                See more information about their <a href="https://bornhack.dk" target="_blank" rel="noopener">previous events</a>! 
                We'll also provide parents with full transparency about accommodations and travel.
            </p>
        </div>

        <div class="faq-item">
            <h2 class="faq-question">How can we trust Hack Club?</h2>
            <p class="faq-answer">
                Hack Club is a 501(c)(3) nonprofit organization. Thousands of students around the world are part of Hack Club, 
                and our finances are completely public and open-source. We've safely run major events like Hack Club Arcade, 
                Assemble, Epoch, and Hack Camp, all designed for teens and supported by our trusted adult mentors. 
                You can learn more about us at <a href="https://hackclub.com" target="_blank" rel="noopener">hackclub.com</a>.
            </p>
        </div>

        <div class="faq-item">
            <h2 class="faq-question">Where can I learn more or get involved?</h2>
            <p class="faq-answer">
                Join the Hack Club community on <a href="https://hackclub.com/slack" target="_blank" rel="noopener">Slack</a> 
                to connect with other hackers heading to BornHack! 
                <span class="wip-note">This is currently a work-in-progress.</span>
            </p>
        </div>
    </div>
</div>
