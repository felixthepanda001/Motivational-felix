# Motivational-felix
Site to help our new generation 
<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>Daily Motivation</title>
<style>
    body {
        font-family: Arial, sans-serif;
        text-align: center;
        background-size: cover;
        background-position: center;
        background-attachment: fixed;
        padding: 50px;
        color: #fff;
        transition: background 0.5s ease-in-out;
    }
    #quote-box {
        background: rgba(0, 0, 0, 0.6);
        border-radius: 10px;
        padding: 30px;
        max-width: 700px;
        margin: auto;
        box-shadow: 0 0 20px rgba(0,0,0,0.5);
    }
    #greeting { font-size: 1.2em; margin-bottom: 10px; }
    #quote { font-size: 1.5em; margin-bottom: 20px; }
    #countdown { font-size: 1em; margin-bottom: 15px; }
    a.affiliate-link, a.resource-link, a.premium-link, a.meal-link {
        display: inline-block;
        margin-top: 10px;
        text-decoration: none;
        color: #fff;
        background: #ff7f50;
        padding: 10px 20px;
        border-radius: 5px;
        transition: background 0.3s;
    }
    a.affiliate-link:hover, a.resource-link:hover, a.premium-link:hover, a.meal-link:hover {
        background: #ff4500;
    }
    #resources, #premium, #meal-plan {
        margin-top: 30px;
        text-align: left;
    }
    h3 { margin-bottom: 10px; }
    ul { list-style: none; padding: 0; }
    li { margin-bottom: 10px; }
    iframe { margin-top: 10px; border-radius: 10px; }
</style>
</head>
<body>

<div id="quote-box">
    <div id="greeting">Hello!</div>
    <div id="quote">Loading quote...</div>
    <div id="countdown"></div>
    <a id="affiliate-link" href="#" target="_blank" class="affiliate-link">Check this out</a>

    <!-- Free Resources -->
    <div id="resources">
        <h3>Educational & Motivational Resources</h3>
        <ul>
            <li><a href="https://www.ted.com/talks" target="_blank" class="resource-link">TED Talks – Inspirational & Educational</a></li>
            <li><a href="https://www.khanacademy.org" target="_blank" class="resource-link">Khan Academy – Learn Anything</a></li>
            <li><a href="https://www.youtube.com/@MotivationHubOfficial" target="_blank" class="resource-link">Motivational YouTube Channel</a></li>
        </ul>
        <iframe width="100%" height="315" src="https://www.youtube.com/embed/ZXsQAXx_ao0" title="Motivational Video" frameborder="0" allowfullscreen></iframe>
    </div>

    <!-- Premium Plan -->
    <div id="premium">
        <h3>💎 Premium $20/month Plan</h3>
        <p>Exclusive content for teens and young adults:</p>
        <ul>
            <li><a href="https://www.example.com/workouts" target="_blank" class="premium-link">Daily Workout Plans</a></li>
            <li><a href="https://www.example.com/pre-workouts" target="_blank" class="premium-link">Pre-Workout Guides</a></li>
            <li><a href="https://www.example.com/training" target="_blank" class="premium-link">Training Programs</a></li>
            <li><a href="https://www.example.com/youthful-success" target="_blank" class="premium-link">Youthful Success Strategies</a></li>
        </ul>
        <p>Subscribe now to unlock your full potential!</p>
    </div>

    <!-- Meal Plan $5 Add-on -->
    <div id="meal-plan">
        <h3>🍽️ Meal Plan Add-On – $5</h3>
        <p>Healthy meal prep ideas and weekly plans:</p>
        <ul>
            <li><a href="https://www.examplemealcompany.com/weekly-plan" target="_blank" class="meal-link">Weekly Meal Prep Guide</a></li>
            <li><a href="https://www.examplemealcompany.com/healthy-recipes" target="_blank" class="meal-link">Healthy Recipes & Tips</a></li>
        </ul>
        <p>Enhance your fitness and energy with structured meal plans!</p>
    </div>
</div>

<!-- Calm background music -->
<audio id="bg-music" autoplay loop>
    <source src="" type="audio/mpeg">
    Your browser does not support the audio element.
</audio>

<script>
    const dailyContent = [
        { quote: "Believe in yourself!", link: "https://www.example-affiliate.com/product1", value: "$5", bg: "https://images.unsplash.com/photo-1506744038136-46273834b3fb?auto=format&fit=crop&w=1600&q=80", music: "https://www.soundhelix.com/examples/mp3/SoundHelix-Song-1.mp3" },
        { quote: "Every day is a second chance.", link: "https://www.example-affiliate.com/product2", value: "$5", bg: "https://images.unsplash.com/photo-1493244040629-496f6d136cc3?auto=format&fit=crop&w=1600&q=80", music: "https://www.soundhelix.com/examples/mp3/SoundHelix-Song-2.mp3" },
        { quote: "Push yourself, because no one else is going to do it for you.", link: "https://www.example-affiliate.com/product3", value: "$5", bg: "https://images.unsplash.com/photo-1507525428034-b723cf961d3e?auto=format&fit=crop&w=1600&q=80", music: "https://www.soundhelix.com/examples/mp3/SoundHelix-Song-3.mp3" },
        { quote: "Dream it. Wish it. Do it.", link: "https://www.example-affiliate.com/product4", value: "$5", bg: "https://images.unsplash.com/photo-1500530855697-b586d89ba3ee?auto=format&fit=crop&w=1600&q=80", music: "https://www.soundhelix.com/examples/mp3/SoundHelix-Song-4.mp3" },
        { quote: "Stay positive, work hard, make it happen.", link: "https://www.example-affiliate.com/product5", value: "$5", bg: "https://images.unsplash.com/photo-1496307042754-b4aa456c4a2d?auto=format&fit=crop&w=1600&q=80", music: "https://www.soundhelix.com/examples/mp3/SoundHelix-Song-5.mp3" }
    ];

    // Determine today's index
    const today = new Date();
    const dayOfYear = Math.floor((today - new Date(today.getFullYear(), 0, 0)) / 1000 / 60 / 60 / 24);
    const index = dayOfYear % dailyContent.length;
    const content = dailyContent[index];

    // Set quote, affiliate link, background
    document.getElementById('quote').textContent = content.quote;
    const affiliateButton = document.getElementById('affiliate-link');
    affiliateButton.href = content.link;
    affiliateButton.textContent = `Check this out – ${content.value}`;
    document.body.style.backgroundImage = `url('${content.bg}')`;

    // Set daily greeting
    const hours = today.getHours();
    let greeting = "Hello!";
    if (hours >= 5 && hours < 12) greeting = "Good morning!";
    else if (hours >= 12 && hours < 17) greeting = "Good afternoon!";
    else greeting = "Good evening!";
    document.getElementById('greeting').textContent = greeting;

    // Countdown to midnight
    function updateCountdown() {
        const now = new Date();
        const midnight = new Date();
        midnight.setHours(24,0,0,0);
        const diff = midnight - now;
        const hrs = Math.floor(diff / 1000 / 60 / 60);
        const mins = Math.floor((diff / 1000 / 60) % 60);
        const secs = Math.floor((diff / 1000) % 60);
        document.getElementById('countdown').textContent = `Time left today: ${hrs}h ${mins}m ${secs}s`;
    }
    setInterval(updateCountdown, 1000);
    updateCountdown();

    // Set daily music
    const musicPlayer = document.getElementById('bg-music');
    musicPlayer.src = content.music;
    musicPlayer.load();
    musicPlayer.play();
</script>

</body>
</html>
