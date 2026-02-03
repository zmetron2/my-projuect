<script>
  let email = '';
  let submitted = false;

  function handleSubmit() {
    if (email) {
      submitted = true;
    }
  }
</script>

<main class="min-h-screen relative overflow-hidden flex flex-col items-center">
  <!-- Hero Background Image -->
  <div class="absolute inset-0 z-0">
    <img src="/hero.png" alt="Hero Background" class="w-full h-full object-cover opacity-60 scale-105 blur-sm" />
    <div class="absolute inset-0 bg-gradient-to-b from-transparent via-[#0f172a]/80 to-[#0f172a]"></div>
  </div>

  <!-- Header -->
  <nav class="relative z-10 w-full max-w-7xl px-8 py-8 flex justify-between items-center">
    <div class="text-2xl font-extrabold tracking-tighter gradient-text">NEXTGEN STUDIO</div>
    <div class="hidden md:flex gap-8 text-sm font-medium text-slate-400">
      <a href="#features" class="text-slate-400 hover:text-white transition-all" style="text-decoration: none;">Features</a>
      <a href="#pricing" class="text-slate-400 hover:text-white transition-all" style="text-decoration: none;">Pricing</a>
      <a href="#about" class="text-slate-400 hover:text-white transition-all" style="text-decoration: none;">About</a>
    </div>
  </nav>

  <!-- Hero Content -->
  <section class="relative z-10 container flex flex-col items-center text-center mt-20 md:mt-32 px-4">
    <div class="inline-block px-4 py-1.5 mb-6 text-xs font-semibold tracking-wider text-indigo-400 uppercase bg-indigo-500/10 border border-indigo-500/20 rounded-full animate-fade-in" style="animation-delay: 0.1s">
      Coming Q2 2026
    </div>
    
    <h1 class="text-5xl md:text-7xl font-black mb-6 leading-tight animate-fade-in text-white" style="animation-delay: 0.2s">
      미래를 위한 최상의<br/>
      <span class="gradient-text">웹사이트 프리오더</span>
    </h1>
    
    <p class="max-w-2xl text-lg md:text-xl text-slate-400 mb-10 animate-fade-in" style="animation-delay: 0.3s">
      평범한 웹사이트를 넘어선 혁신적인 사용자 경험. <br class="hidden md:block"/>
      NextGen Studio와 함께 다음 세대의 디지털 존재감을 먼저 확보하세요.
    </p>

    <!-- Pre-order Form -->
    <div class="glass p-8 md:p-10 w-full max-w-xl animate-fade-in" style="animation-delay: 0.4s">
      {#if !submitted}
        <h3 class="text-xl font-bold mb-4 text-white">지금 예약하고 20% 얼리버드 혜택 받기</h3>
        <form on:submit|preventDefault={handleSubmit} class="flex flex-col md:flex-row gap-4">
          <input 
            type="email" 
            placeholder="이메일 주소를 입력하세요" 
            bind:value={email}
            required
            class="flex-1 bg-slate-900/50 border border-white/10 rounded-xl px-4 py-3 text-white focus:outline-none transition-all"
            style="color: white; border: 1px solid rgba(255,255,255,0.1);"
          />
          <button type="submit" class="btn-primary whitespace-nowrap">
            예약 주문 신청
          </button>
        </form>
        <p class="mt-4 text-xs text-slate-500">신청 시 개인정보 수집 및 마케팅 활용에 동의하게 됩니다.</p>
      {:else}
        <div class="text-center py-8">
          <div class="inline-flex items-center justify-center w-16 h-16 bg-emerald-500/20 rounded-full mb-4 mx-auto">
            <svg class="w-8 h-8 text-emerald-500" fill="none" stroke="currentColor" viewBox="0 0 24 24" style="width: 32px; height: 32px;">
              <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M5 13l4 4L19 7"></path>
            </svg>
          </div>
          <h3 class="text-2xl font-bold mb-2 text-white">예약이 완료되었습니다!</h3>
          <p class="text-slate-400">입력하신 <strong>{email}</strong>로 출시 소식을 가장 먼저 보내드릴게요.</p>
        </div>
      {/if}
    </div>

    <!-- Stats -->
    <div class="grid grid-cols-2 md:grid-cols-4 gap-8 mt-24 w-full max-w-4xl border-t border-white/5 pt-12 animate-fade-in" style="animation-delay: 0.5s">
      <div class="text-center">
        <div class="text-3xl font-extrabold text-white">450+</div>
        <div class="text-xs text-slate-500 uppercase tracking-widest mt-1">예약 완료</div>
      </div>
      <div class="text-center">
        <div class="text-3xl font-extrabold text-white">99.9%</div>
        <div class="text-xs text-slate-500 uppercase tracking-widest mt-1">고객 만족도</div>
      </div>
      <div class="text-center">
        <div class="text-3xl font-extrabold text-white">20%</div>
        <div class="text-xs text-slate-500 uppercase tracking-widest mt-1">할인 혜택</div>
      </div>
      <div class="text-center">
        <div class="text-3xl font-extrabold text-white">24/7</div>
        <div class="text-xs text-slate-500 uppercase tracking-widest mt-1">전문가 지원</div>
      </div>
    </div>
  </section>

  <div style="height: 8rem;"></div>
</main>

<style>
  /* Simplified scoped styles for specific tweaks */
  .mx-auto { margin-left: auto; margin-right: auto; }
</style>
