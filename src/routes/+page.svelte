<script>
  let email = '';
  let submitted = false;
  let isLoading = false; // 로딩 상태 추가

  // ⚠️ 1단계에서 복사한 '웹 앱 URL'을 아래 따옴표 안에 넣어주세요!
  const GOOGLE_SCRIPT_URL = 'https://script.google.com/macros/s/AKfycbw06fZtjjLdDLZW04uJWFRubJ2_8Ee-2EGVYsGtbra29v2EIap4vzhSrOl32J1e7hXn3Q/exec';

  async function handleSubmit() {
    if (!email) return;
    
    // URL이 설정되지 않았을 때 안내
    if (GOOGLE_SCRIPT_URL.includes('여기에_')) {
        alert('개발자님! Google Apps Script 배포 URL을 코드에 입력해주세요.');
        return;
    }

    isLoading = true;

    try {
        const formData = new FormData();
        formData.append('email', email);
        formData.append('date', new Date().toLocaleString('ko-KR')); // 한국 시간 기록

        // 구글 스크립트로 전송
        await fetch(GOOGLE_SCRIPT_URL, {
            method: 'POST',
            body: formData,
            mode: 'no-cors' // 구글 시트 CORS 에러 방지용 (응답 내용을 읽진 못해도 전송은 됨)
        });

        // no-cors 모드에서는 항상 성공으로 간주하고 처리 (실제 실패율 매우 낮음)
        submitted = true;
        
    } catch (error) {
        console.error('Error:', error);
        alert('전송 중 오류가 발생했습니다. 잠시 후 다시 시도해주세요.');
    } finally {
        isLoading = false;
    }
  }
</script>

<style>
    :global(body) {
        font-family: 'Inter', 'Noto Sans KR', sans-serif;
        -webkit-font-smoothing: antialiased;
        word-break: keep-all;
    }
    .glass-card {
        background: rgba(255, 255, 255, 0.7);
        backdrop-filter: blur(12px);
        border: 1px solid rgba(255, 255, 255, 0.8);
    }
    .hero-gradient {
        background: radial-gradient(circle at 50% 50%, rgba(124, 58, 237, 0.08) 0%, transparent 70%);
    }
    .text-gradient {
        background: linear-gradient(135deg, #7C3AED 0%, #3B82F6 100%);
        -webkit-background-clip: text;
        -webkit-text-fill-color: transparent;
        background-clip: text;
    }
    @media (min-width: 1024px) {
        .bottom-nav-hide {
            display: none;
        }
    }
</style>

<div class="bg-background-light dark:bg-background-dark text-slate-900 dark:text-slate-100 min-h-screen overflow-x-hidden">

    <!-- Spacer for navigation -->
    <div class="h-8 w-full lg:h-12"></div>

    <!-- Navigation -->
    <nav class="px-4 sm:px-6 lg:px-8 xl:px-12 py-3 lg:py-5 relative z-10">
        <div class="max-w-7xl mx-auto flex justify-between items-center">
            <div class="flex items-center gap-2 lg:gap-3">
                <div class="w-7 h-7 sm:w-8 sm:h-8 lg:w-10 lg:h-10 bg-primary rounded-lg flex items-center justify-center">
                    <span class="material-icons text-white text-lg sm:text-xl lg:text-2xl">rocket_launch</span>
                </div>
                <span class="font-extrabold text-base sm:text-xl lg:text-2xl tracking-tight text-slate-900 dark:text-white">NEXTGEN STUDIO</span>
            </div>
            
            <!-- Desktop Navigation Menu -->
            <div class="hidden lg:flex items-center gap-8">
                <a href="#" class="text-sm font-semibold text-slate-700 dark:text-slate-300 hover:text-primary transition">홈</a>
                <a href="#" class="text-sm font-semibold text-slate-700 dark:text-slate-300 hover:text-primary transition">둘러보기</a>
                <a href="#" class="text-sm font-semibold text-slate-700 dark:text-slate-300 hover:text-primary transition">사전 예약</a>
                <a href="#" class="text-sm font-semibold text-slate-700 dark:text-slate-300 hover:text-primary transition">프로필</a>
            </div>
            
            <!-- Mobile menu button -->
            <button class="lg:hidden w-9 h-9 sm:w-10 sm:h-10 rounded-full flex items-center justify-center bg-white/50 dark:bg-white/10 border border-slate-200 dark:border-slate-700 hover:bg-white/70 dark:hover:bg-white/20 transition">
                <span class="material-icons text-lg sm:text-xl">menu</span>
            </button>
        </div>
    </nav>

    <!-- Main Content -->
    <main class="px-4 sm:px-6 lg:px-8 xl:px-12 pt-8 sm:pt-12 lg:pt-16 xl:pt-20 pb-24 lg:pb-32 relative">
        <!-- Background Gradients -->
        <div class="absolute top-10 sm:top-20 left-1/2 -translate-x-1/2 w-[140%] lg:w-[100%] h-[500px] lg:h-[700px] hero-gradient pointer-events-none -z-10"></div>
        <div class="absolute -top-10 -right-20 lg:-right-32 w-48 h-48 sm:w-64 sm:h-64 lg:w-96 lg:h-96 bg-accent-purple/10 rounded-full blur-3xl pointer-events-none -z-10"></div>
        <div class="absolute top-40 -left-20 lg:-left-32 w-48 h-48 sm:w-64 sm:h-64 lg:w-96 lg:h-96 bg-accent-blue/10 rounded-full blur-3xl pointer-events-none -z-10"></div>
        
        <!-- Content Container -->
        <div class="max-w-7xl mx-auto">
            <div class="flex flex-col items-center text-center">
                <!-- Badge -->
                <div class="inline-flex items-center px-3 sm:px-4 py-1.5 rounded-full bg-primary/10 border border-primary/20 mb-6 sm:mb-8">
                    <span class="text-[10px] sm:text-xs font-bold tracking-widest text-primary uppercase">2026년 2분기 출시 예정</span>
                </div>
                
                <!-- Heading -->
                <h1 class="text-3xl xs:text-4xl sm:text-5xl lg:text-6xl xl:text-7xl font-extrabold leading-[1.2] mb-4 sm:mb-6 tracking-tight max-w-5xl">
                    최고의 웹사이트 <br class="sm:hidden"/>
                    <span class="text-gradient">미래를 선점하세요</span>
                </h1>
                
                <!-- Description -->
                <p class="text-slate-500 dark:text-slate-400 text-sm sm:text-base lg:text-lg leading-relaxed max-w-xs sm:max-w-md lg:max-w-2xl mb-8 sm:mb-12 lg:mb-16 px-4">
                    평범함을 뛰어넘는 혁신적인 사용자 경험, 오늘 NextGen Studio와 함께 차세대 디지털 프레즌스를 확보하세요.
                </p>
                
                <!-- Form Card -->
                <div class="w-full max-w-md lg:max-w-lg xl:max-w-xl glass-card p-5 sm:p-6 lg:p-8 xl:p-10 rounded-2xl sm:rounded-3xl shadow-2xl shadow-slate-200/50 dark:shadow-none border border-white/40 dark:border-white/5">
                    
                    {#if !submitted}
                        <div class="flex items-center justify-center gap-2 mb-5 sm:mb-6">
                            <span class="material-icons text-primary text-xl sm:text-2xl">auto_awesome</span>
                            <h2 class="text-base sm:text-lg lg:text-xl font-bold">20% 얼리버드 혜택</h2>
                        </div>
                        
                        <form on:submit|preventDefault={handleSubmit} class="space-y-3 sm:space-y-4">
                            <div class="relative">
                                <span class="material-icons absolute left-3 sm:left-4 top-1/2 -translate-y-1/2 text-slate-400 text-xl">mail_outline</span>
                                <input 
                                    class="w-full pl-10 sm:pl-12 pr-3 sm:pr-4 py-3 sm:py-4 text-sm sm:text-base bg-white/80 dark:bg-slate-800/80 border border-slate-200 dark:border-slate-700 rounded-xl sm:rounded-2xl focus:ring-2 focus:ring-primary focus:border-transparent transition-all outline-none text-slate-900 dark:text-white placeholder:text-slate-400" 
                                    placeholder="이메일 주소를 입력해주세요" 
                                    type="email"
                                    bind:value={email}
                                    required
                                />
                            </div>
                            
                            <button disabled={isLoading} class="w-full bg-primary hover:bg-primary/90 disabled:opacity-70 disabled:cursor-not-allowed text-white font-bold py-3 sm:py-4 text-sm sm:text-base rounded-xl sm:rounded-2xl shadow-lg shadow-primary/30 transition-all active:scale-[0.98] flex items-center justify-center gap-2">
                                {#if isLoading}
                                    <span>처리 중...</span>
                                {:else}
                                    지금 사전 예약하기
                                    <span class="material-icons text-sm sm:text-base">arrow_forward</span>
                                {/if}
                            </button>
                        </form>
                        
                        <p class="mt-5 sm:mt-6 text-[10px] sm:text-[11px] text-slate-400 dark:text-slate-500 leading-normal">
                            가입 시 데이터 수집 및 마케팅 활용 정책에 동의하게 됩니다. 고객님의 개인정보는 안전하게 보호됩니다.
                        </p>
                    {:else}
                        <div class="py-8 text-center">
                            <div class="w-16 h-16 bg-emerald-500/20 rounded-full flex items-center justify-center mx-auto mb-4">
                                <span class="material-icons text-emerald-500 text-3xl">check</span>
                            </div>
                            <h3 class="text-xl font-bold text-slate-900 dark:text-white mb-2">예약이 완료되었습니다!</h3>
                            <p class="text-slate-500">서비스 출시 시 <strong>{email}</strong>(으)로 알려드리겠습니다.</p>
                        </div>
                    {/if}

                </div>
                
                <!-- Stats -->
                <div class="mt-12 sm:mt-16 lg:mt-20 flex flex-wrap justify-center gap-6 sm:gap-8 lg:gap-12 opacity-60">
                    <div class="flex flex-col items-center">
                        <span class="text-xl sm:text-2xl lg:text-3xl font-bold">99%</span>
                        <span class="text-[9px] sm:text-[10px] lg:text-xs uppercase tracking-widest font-semibold mt-1">만족도</span>
                    </div>
                    <div class="flex flex-col items-center">
                        <span class="text-xl sm:text-2xl lg:text-3xl font-bold">24/7</span>
                        <span class="text-[9px] sm:text-[10px] lg:text-xs uppercase tracking-widest font-semibold mt-1">고객 지원</span>
                    </div>
                    <div class="flex flex-col items-center">
                        <span class="text-xl sm:text-2xl lg:text-3xl font-bold">50+</span>
                        <span class="text-[9px] sm:text-[10px] lg:text-xs uppercase tracking-widest font-semibold mt-1">템플릿</span>
                    </div>
                </div>
            </div>
        </div>
    </main>

    <!-- Bottom Navigation - Hidden on Desktop -->
    <div class="bottom-nav-hide fixed bottom-0 left-0 right-0 bg-white/80 dark:bg-slate-900/80 backdrop-blur-xl border-t border-slate-200 dark:border-slate-800 px-4 sm:px-6 pt-2 sm:pt-3 pb-6 sm:pb-8 flex justify-around items-center z-50">
        <div class="flex flex-col items-center gap-0.5 sm:gap-1 text-primary">
            <span class="material-icons text-xl sm:text-2xl">home</span>
            <span class="text-[9px] sm:text-[10px] font-bold">홈</span>
        </div>
        <div class="flex flex-col items-center gap-0.5 sm:gap-1 text-slate-400 hover:text-primary transition cursor-pointer">
            <span class="material-icons text-xl sm:text-2xl">explore</span>
            <span class="text-[9px] sm:text-[10px] font-medium">둘러보기</span>
        </div>
        <div class="flex flex-col items-center gap-0.5 sm:gap-1 text-slate-400 hover:text-primary transition cursor-pointer">
            <span class="material-icons text-xl sm:text-2xl">shopping_bag</span>
            <span class="text-[9px] sm:text-[10px] font-medium">사전 예약</span>
        </div>
        <div class="flex flex-col items-center gap-0.5 sm:gap-1 text-slate-400 hover:text-primary transition cursor-pointer">
            <span class="material-icons text-xl sm:text-2xl">person_outline</span>
            <span class="text-[9px] sm:text-[10px] font-medium">프로필</span>
        </div>
    </div>

    <!-- Grid Background -->
    <div class="fixed top-1/2 left-1/2 -translate-x-1/2 -translate-y-1/2 w-full h-full pointer-events-none overflow-hidden -z-20 opacity-30 dark:opacity-10">
        <svg height="100%" width="100%" xmlns="http://www.w3.org/2000/svg">
            <defs>
                <pattern height="40" id="grid" patternUnits="userSpaceOnUse" width="40">
                    <path d="M 40 0 L 0 0 0 40" fill="none" stroke="currentColor" stroke-width="0.5"></path>
                </pattern>
            </defs>
            <rect fill="url(#grid)" height="100%" width="100%"></rect>
        </svg>
    </div>

</div>
