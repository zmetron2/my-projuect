<script>
  let email = '';
  let submitted = false;

  function handleSubmit() {
    if (email) {
      submitted = true;
    }
  }
</script>

<div class="h-12 w-full"></div>

<nav class="px-6 py-4 flex justify-between items-center relative z-10">
  <div class="flex items-center gap-2">
    <div class="w-8 h-8 bg-primary rounded-lg flex items-center justify-center">
      <span class="material-icons text-white text-xl">rocket_launch</span>
    </div>
    <span class="font-extrabold text-xl tracking-tight">NEXTGEN STUDIO</span>
  </div>
  <button class="w-10 h-10 rounded-full flex items-center justify-center bg-white/10 border border-white/10">
    <span class="material-icons text-xl text-white">menu</span>
  </button>
</nav>

<main class="px-6 pt-12 pb-24 relative">
  <!-- Hero Gradients -->
  <div class="absolute top-20 left-1/2 -translate-x-1/2 w-full h-[500px] hero-gradient pointer-events-none -z-10" style="transform: translateX(-50%);"></div>
  
  <div class="flex flex-col items-center text-center">
    <!-- Coming Soon Badge -->
    <div class="inline-flex items-center px-4 py-1.5 rounded-full bg-primary/10 border border-primary/20 mb-8" style="background: rgba(124, 58, 237, 0.1); border: 1px solid rgba(124, 58, 237, 0.2);">
      <span class="text-xs font-bold tracking-widest text-primary uppercase">COMING Q2 2026</span>
    </div>

    <!-- Title -->
    <h1 class="text-4xl md:text-5xl font-extrabold mb-6 tracking-tight leading-tight">
      The Best Website <br/>
      <span class="text-gradient">Pre-order for the Future</span>
    </h1>

    <!-- Description -->
    <p class="text-slate-400 text-base leading-relaxed max-w-2xl mb-12 mx-auto">
      Revolutionary user experiences that go beyond ordinary websites. Secure your next-generation digital presence with NextGen Studio today.
    </p>

    <!-- Glass Card -->
    <div class="w-full glass-card p-6 md:p-8 max-w-xl mx-auto">
      {#if !submitted}
        <div class="flex items-center justify-center gap-2 mb-6 text-primary">
          <span class="material-icons">auto_awesome</span>
          <h2 class="text-lg font-bold text-white">20% Early Bird Benefit</h2>
        </div>

        <form on:submit|preventDefault={handleSubmit} class="flex flex-col gap-4">
          <div class="relative">
            <span class="material-icons absolute left-4 text-slate-400" style="top: 50%; transform: translateY(-50%);">mail_outline</span>
            <input 
              class="input-field" 
              placeholder="Enter your email address" 
              type="email"
              bind:value={email}
              required
            />
          </div>
          <button class="btn-submit flex items-center justify-center gap-2">
            Pre-order Now
            <span class="material-icons text-sm">arrow_forward</span>
          </button>
        </form>

        <p class="mt-6 text-xs text-slate-500 leading-normal">
          By signing up, you agree to our data collection and marketing usage policies. We respect your privacy.
        </p>
      {:else}
        <div class="py-8">
          <div class="w-16 h-16 bg-emerald-500/20 rounded-full flex items-center justify-center mx-auto mb-4" style="background: rgba(16, 185, 129, 0.2);">
            <span class="material-icons text-emerald-500 text-3xl">check</span>
          </div>
          <h3 class="text-xl font-bold text-white mb-2">Pre-order Complete!</h3>
          <p class="text-slate-400">We'll notify <strong>{email}</strong> when we launch.</p>
        </div>
      {/if}
    </div>

    <!-- Stats -->
    <div class="mt-16 flex flex-wrap justify-center gap-8 opacity-60">
      <div class="flex flex-col items-center">
        <span class="text-2xl font-bold">99%</span>
        <span class="text-xs uppercase tracking-widest font-semibold p-2">Satisfaction</span>
      </div>
      <div class="flex flex-col items-center">
        <span class="text-2xl font-bold">24/7</span>
        <span class="text-xs uppercase tracking-widest font-semibold p-2">Support</span>
      </div>
      <div class="flex flex-col items-center">
        <span class="text-2xl font-bold">50+</span>
        <span class="text-xs uppercase tracking-widest font-semibold p-2">Templates</span>
      </div>
    </div>
  </div>
</main>

<!-- Navigation Bottom -->
<div class="fixed bottom-0 left-0 right-0 bg-[#0F172A]/80 backdrop-blur-xl border-t border-white/10 px-6 pt-3 pb-8 flex justify-around items-center z-50">
  <div class="flex flex-col items-center gap-1 text-primary">
    <span class="material-icons">home</span>
    <span class="text-xs font-bold">Home</span>
  </div>
  <div class="flex flex-col items-center gap-1 text-slate-400">
    <span class="material-icons">explore</span>
    <span class="text-xs">Explore</span>
  </div>
  <div class="flex flex-col items-center gap-1 text-slate-400">
    <span class="material-icons">shopping_bag</span>
    <span class="text-xs">Pre-order</span>
  </div>
  <div class="flex flex-col items-center gap-1 text-slate-400">
    <span class="material-icons">person_outline</span>
    <span class="text-xs">Profile</span>
  </div>
</div>

<!-- Grid Background Overlay -->
<div class="fixed inset-0 pointer-events-none -z-20 opacity-10 bg-grid"></div>

<style>
  .mx-auto { margin-left: auto; margin-right: auto; }
</style>
