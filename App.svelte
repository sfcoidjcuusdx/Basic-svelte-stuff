<script>
  import { Home, Star, Settings, BookOpen, Mail } from 'lucide-svelte';
  let activeTab = "home";
</script>

<style>
  @import url('https://fonts.googleapis.com/css2?family=Poppins:wght@300;500;700&display=swap');

  body {
    font-family: 'Poppins', sans-serif;
    background-color: #121417;
    color: #e4e6eb;
    margin: 0;
    min-height: 100vh;
    -webkit-font-smoothing: antialiased;
    -moz-osx-font-smoothing: grayscale;
  }

  nav {
    display: flex;
    justify-content: center;
    gap: 2rem;
    background: linear-gradient(90deg, #0d1117, #161b22);
    padding: 1.25rem 1rem;
    box-shadow: 0 4px 12px rgba(0, 0, 0, 0.85);
  }

  nav button {
    background: none;
    border: none;
    color: #8b949e;
    font-size: 1.15rem;
    display: flex;
    align-items: center;
    gap: 0.6rem;
    cursor: pointer;
    transition: color 0.25s ease, transform 0.2s ease;
    font-weight: 500;
    padding: 0.3rem 0.5rem;
    border-radius: 8px;
  }

  nav button:hover {
    color: #58a6ff;
    transform: scale(1.1);
  }

  nav button.active {
    font-weight: 700;
    color: #58a6ff;
    text-decoration: underline;
    transform: scale(1.15);
  }

  nav svg {
    stroke: currentColor;
  }

  main {
    max-width: 960px;
    margin: 2.5rem auto;
    padding: 2rem 2.5rem;
    background-color: #0d1117;
    border-radius: 20px;
    box-shadow:
      0 10px 30px rgb(88 166 255 / 0.15),
      0 4px 8px rgb(15 23 42 / 0.25);
  }

  h1 {
    color: #58a6ff;
    font-weight: 700;
    font-size: 2.8rem;
    margin-bottom: 1.25rem;
    letter-spacing: -0.03em;
    user-select: none;
  }

  .card {
    background-color: #161b22;
    padding: 2rem;
    border-radius: 16px;
    margin-bottom: 1.8rem;
    box-shadow:
      0 6px 12px rgb(88 166 255 / 0.12);
    transition: transform 0.3s ease, box-shadow 0.3s ease;
  }

  .card:hover {
    transform: translateY(-6px);
    box-shadow:
      0 12px 24px rgb(88 166 255 / 0.3);
  }

  .card h2 {
    color: #79c0ff;
    font-weight: 600;
    font-size: 1.65rem;
    margin-bottom: 0.5rem;
  }

  p {
    color: #c9d1d9;
    font-size: 1.12rem;
    line-height: 1.6;
    user-select: text;
  }

  a {
    color: #58a6ff;
    font-weight: 600;
    text-decoration: none;
    cursor: pointer;
  }

  a:hover {
    text-decoration: underline;
    color: #79c0ff;
  }
</style>

<nav>
  <button on:click={() => activeTab = "home"} class:active={activeTab === "home"}>
    <Home size="20" /> Home
  </button>
  <button on:click={() => activeTab = "features"} class:active={activeTab === "features"}>
    <Star size="20" /> Features
  </button>
  <button on:click={() => activeTab = "tools"} class:active={activeTab === "tools"}>
    <Settings size="20" /> CBT Tools
  </button>
  <button on:click={() => activeTab = "plan"} class:active={activeTab === "plan"}>
    <BookOpen size="20" /> Recovery Plan
  </button>
  <button on:click={() => activeTab = "contact"} class:active={activeTab === "contact"}>
    <Mail size="20" /> Contact
  </button>
</nav>

<main>
  {#if activeTab === "home"}
    <h1>Welcome to LoopLess</h1>
    <div class="card">
      <h2>Take Back Control</h2>
      <p>LoopLess helps you break free from compulsive screen habits with personalized tools grounded in cognitive behavioral therapy (CBT).</p>
    </div>
  {/if}

  {#if activeTab === "features"}
    <h1>Features</h1>
    <div class="card">
      <h2>Tailored App Recovery</h2>
      <p>Custom recovery plans for TikTok, Instagram, YouTube, Reddit, and more — based on their specific design traps.</p>
    </div>
    <div class="card">
      <h2>Mood & Emotion Sync</h2>
      <p>See how your screen time leads to mood changes and emotional triggers over time.</p>
    </div>
    <div class="card">
      <h2>Daily Journaling</h2>
      <p>Record your insights, progress, and reflections as you become less dependent on your screen.</p>
    </div>
  {/if}

  {#if activeTab === "tools"}
    <h1>CBT-Based Tools</h1>
    <div class="card">
      <h2>Thought Records</h2>
      <p>Break down and analyze unhealthy thought loops that drive compulsive checking.</p>
    </div>
    <div class="card">
      <h2>Behavioral Experiments</h2>
      <p>Run experimental tests to disprove the “I’ll miss out” or “I can’t function without it” myths. These can also help you grow in tandem with journaling. </p>
    </div>
    <div class="card">
      <h2>Trigger Exposure</h2>
      <p>Gradually get comfortable with boredom, silence, or waiting (without reaching for a screen).</p>
    </div>
  {/if}

  {#if activeTab === "plan"}
    <h1>Recovery Plan</h1>
    <div class="card">
      <h2>Set Your Goals</h2>
      <p>Build SMART goals — specific, measurable, achievable, relevant, and time-bound. I can get rid of this if you want, Zach. </p>
    </div>
    <div class="card">
      <h2>Create Screen-Free Rituals</h2>
      <p>Fill your life with new routines: mindfulness, music, creativity, movement, or connection.</p>
    </div>
    <div class="card">
      <h2>Track Your Progress</h2>
      <p>Visualize your growth and celebrate every day you reclaim.</p>
    </div>
  {/if}

  {#if activeTab === "contact"}
    <h1>Contact</h1>
    <div class="card">
      <h2>Talk to Us</h2>
      <p>Email: <a href="mailto:support@looplessapp.com">support@looplessapp.com</a></p>
    </div>
    <div class="card">
      <h2>Join Our Community</h2>
      <p>Get tips and support from others embracing a more screen-free life.</p>
    </div>
  {/if}
</main>
