<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Viral Video Hub - Watch Trending Videos</title>
    <!-- Tailwind CSS for Styling -->
    <script src="https://cdn.tailwindcss.com"></script>
    <!-- Google Fonts -->
    <link href="https://fonts.googleapis.com/css2?family=Inter:wght@400;500;700&display=swap" rel="stylesheet">
    <style>
        body {
            font-family: 'Inter', sans-serif;
            background-color: #0f172a; /* Dark theme for video sites */
            color: #f8fafc;
        }
        /* Hover effect for play button */
        .play-btn-glow {
            filter: drop-shadow(0 0 10px rgba(239, 68, 68, 0.8));
        }
        /* Limit title to 2 lines */
        .line-clamp-2 {
            display: -webkit-box;
            -webkit-line-clamp: 2;
            -webkit-box-orient: vertical;  
            overflow: hidden;
        }
        
        /* Spinner Animation for Fake Loading */
        @keyframes spin-slow {
            0% { transform: rotate(0deg); }
            100% { transform: rotate(360deg); }
        }
        .spin-slow {
            animation: spin-slow 1.5s linear infinite;
        }
    </style>
</head>
<body class="min-h-screen flex flex-col">

    <!-- Navbar -->
    <header class="bg-gray-900 border-b border-gray-800 sticky top-0 z-50">
        <div class="max-w-7xl mx-auto px-4 sm:px-6 lg:px-8 h-16 flex items-center justify-between">
            <div class="flex items-center gap-2 cursor-pointer">
                <svg class="w-8 h-8 text-red-500" fill="currentColor" viewBox="0 0 24 24">
                    <path d="M19.615 3.184c-3.604-.246-11.631-.245-15.23 0-3.897.266-4.356 2.62-4.385 8.816.029 6.185.484 8.549 4.385 8.816 3.6.245 11.626.246 15.23 0 3.897-.266 4.356-2.62 4.385-8.816-.029-6.185-.484-8.549-4.385-8.816zm-10.615 12.816v-8l8 3.993-8 4.007z"/>
                </svg>
                <span class="text-xl font-bold tracking-tight">Viral<span class="text-red-500">Hub</span></span>
            </div>
            <!-- Optional Top CTA for Adsterra -->
            <a href="[আপনার Adsterra Link]" target="_blank" class="bg-red-600 hover:bg-red-700 text-white px-4 py-2 rounded-full text-sm font-semibold transition-colors shadow-[0_0_15px_rgba(220,38,38,0.5)] animate-pulse">
                🔥 Premium Videos
            </a>
        </div>
    </header>

    <!-- Main Content -->
    <main class="flex-grow max-w-7xl mx-auto px-4 sm:px-6 lg:px-8 py-8 w-full">
        
        <div class="mb-8 flex justify-between items-end">
            <div>
                <h1 class="text-2xl md:text-3xl font-bold text-white mb-2">🔥 Trending Right Now</h1>
                <p class="text-gray-400 text-sm md:text-base">Watch the most viral videos on the internet today.</p>
            </div>
        </div>

        <!-- Video Grid Container -->
        <div class="grid grid-cols-1 sm:grid-cols-2 md:grid-cols-3 lg:grid-cols-4 gap-6">

            <!-- 
            ======================================================================
            👇👇👇 এখান থেকে একটি ভিডিও কার্ড শুরু 👇👇👇 
            ====================================================================== 
            -->
            <!-- Video 1 -->
            <a href="[আপনার Adsterra Direct Link এখানে দিন]" target="_blank" class="block group cursor-pointer">
                <!-- Thumbnail Area -->
                <div class="relative rounded-xl overflow-hidden aspect-video bg-gray-800 border border-gray-700">
                    <!-- Thumbnail Image (Change src to your image link) -->
                    <img src="https://placehold.co/600x338/1e293b/ef4444?text=Bangla+Viral+18%2B" alt="Video Thumbnail" class="object-cover w-full h-full group-hover:scale-105 transition-transform duration-500">
                    
                    <!-- Play Button Overlay -->
                    <div class="absolute inset-0 bg-black bg-opacity-30 flex items-center justify-center group-hover:bg-opacity-40 transition-all">
                        <svg class="w-14 h-14 text-white opacity-90 group-hover:text-red-500 group-hover:play-btn-glow transition-all duration-300" fill="currentColor" viewBox="0 0 24 24">
                            <path d="M8 5v14l11-7z"/>
                        </svg>
                    </div>
                    
                    <!-- Fake Duration Badge -->
                    <div class="absolute bottom-2 right-2 bg-black bg-opacity-80 px-2 py-1 text-xs font-semibold rounded">
                        12:45
                    </div>
                    
                    <!-- 18+ Badge -->
                    <div class="absolute top-2 left-2 bg-red-600 px-2 py-1 text-xs font-bold text-white rounded">
                        18+ Only
                    </div>
                </div>
                
                <!-- Video Details -->
                <div class="mt-3">
                    <h3 class="text-base font-semibold text-gray-100 group-hover:text-red-400 transition-colors line-clamp-2">
                        Bangla Viral MMS Leaked Full Video 🔞 Watch Before Delete
                    </h3>
                    <div class="flex items-center text-xs text-gray-400 mt-1.5 gap-2">
                        <span>3.2M views</span>
                        <span>•</span>
                        <span>1 hour ago</span>
                    </div>
                </div>
            </a>
            <!-- 👆👆👆 ভিডিও কার্ড শেষ 👆👆👆 -->


            <!-- Video 2 -->
            <a href="[আপনার Adsterra Direct Link এখানে দিন]" target="_blank" class="block group cursor-pointer">
                <div class="relative rounded-xl overflow-hidden aspect-video bg-gray-800 border border-gray-700">
                    <img src="https://placehold.co/600x338/1e293b/ef4444?text=Kolkata+Scandal" alt="Video Thumbnail" class="object-cover w-full h-full group-hover:scale-105 transition-transform duration-500">
                    <div class="absolute inset-0 bg-black bg-opacity-30 flex items-center justify-center group-hover:bg-opacity-40 transition-all">
                        <svg class="w-14 h-14 text-white opacity-90 group-hover:text-red-500 group-hover:play-btn-glow transition-all duration-300" fill="currentColor" viewBox="0 0 24 24"><path d="M8 5v14l11-7z"/></svg>
                    </div>
                    <div class="absolute bottom-2 right-2 bg-black bg-opacity-80 px-2 py-1 text-xs font-semibold rounded">08:20</div>
                    <div class="absolute top-2 left-2 bg-red-600 px-2 py-1 text-xs font-bold text-white rounded">Viral</div>
                </div>
                <div class="mt-3">
                    <h3 class="text-base font-semibold text-gray-100 group-hover:text-red-400 transition-colors line-clamp-2">
                        Kolkata Model Hidden Camera Scandal Video Uncensored 😱
                    </h3>
                    <div class="flex items-center text-xs text-gray-400 mt-1.5 gap-2">
                        <span>1.8M views</span>
                        <span>•</span>
                        <span>3 hours ago</span>
                    </div>
                </div>
            </a>

            <!-- Video 3 -->
            <a href="[আপনার Adsterra Direct Link এখানে দিন]" target="_blank" class="block group cursor-pointer">
                <div class="relative rounded-xl overflow-hidden aspect-video bg-gray-800 border border-gray-700">
                    <img src="https://placehold.co/600x338/1e293b/ef4444?text=TikToker+Leaked" alt="Video Thumbnail" class="object-cover w-full h-full group-hover:scale-105 transition-transform duration-500">
                    <div class="absolute inset-0 bg-black bg-opacity-30 flex items-center justify-center group-hover:bg-opacity-40 transition-all">
                        <svg class="w-14 h-14 text-white opacity-90 group-hover:text-red-500 group-hover:play-btn-glow transition-all duration-300" fill="currentColor" viewBox="0 0 24 24"><path d="M8 5v14l11-7z"/></svg>
                    </div>
                    <div class="absolute bottom-2 right-2 bg-black bg-opacity-80 px-2 py-1 text-xs font-semibold rounded">04:15</div>
                    <div class="absolute top-2 left-2 bg-red-600 px-2 py-1 text-xs font-bold text-white rounded">18+ Only</div>
                </div>
                <div class="mt-3">
                    <h3 class="text-base font-semibold text-gray-100 group-hover:text-red-400 transition-colors line-clamp-2">
                        Bangladeshi TikToker Private Room Video Leaked! (Full HD)
                    </h3>
                    <div class="flex items-center text-xs text-gray-400 mt-1.5 gap-2">
                        <span>5.1M views</span>
                        <span>•</span>
                        <span>45 mins ago</span>
                    </div>
                </div>
            </a>

            <!-- Video 4 -->
            <a href="[আপনার Adsterra Direct Link এখানে দিন]" target="_blank" class="block group cursor-pointer">
                <div class="relative rounded-xl overflow-hidden aspect-video bg-gray-800 border border-gray-700">
                    <img src="https://placehold.co/600x338/1e293b/ef4444?text=Resort+Scandal" alt="Video Thumbnail" class="object-cover w-full h-full group-hover:scale-105 transition-transform duration-500">
                    <div class="absolute inset-0 bg-black bg-opacity-30 flex items-center justify-center group-hover:bg-opacity-40 transition-all">
                        <svg class="w-14 h-14 text-white opacity-90 group-hover:text-red-500 group-hover:play-btn-glow transition-all duration-300" fill="currentColor" viewBox="0 0 24 24"><path d="M8 5v14l11-7z"/></svg>
                    </div>
                    <div class="absolute bottom-2 right-2 bg-black bg-opacity-80 px-2 py-1 text-xs font-semibold rounded">21:05</div>
                    <div class="absolute top-2 left-2 bg-red-600 px-2 py-1 text-xs font-bold text-white rounded">Exclusive</div>
                </div>
                <div class="mt-3">
                    <h3 class="text-base font-semibold text-gray-100 group-hover:text-red-400 transition-colors line-clamp-2">
                        Cox's Bazar Hotel Hidden Cam Full Footage Released 🚨
                    </h3>
                    <div class="flex items-center text-xs text-gray-400 mt-1.5 gap-2">
                        <span>800K views</span>
                        <span>•</span>
                        <span>2 days ago</span>
                    </div>
                </div>
            </a>

            <!-- আরও ভিডিও যোগ করার জন্য উপরের যেকোনো একটি ভিডিও কার্ড কপি করে এখানে পেস্ট করুন -->

        </div>

        <!-- Load More Button (Fake function to redirect to Adsterra) -->
        <div class="mt-12 text-center">
            <a href="[আপনার Adsterra Direct Link এখানে দিন]" target="_blank" class="inline-block bg-gray-800 hover:bg-gray-700 text-white border border-gray-600 px-8 py-3 rounded-lg font-semibold transition-colors">
                Load More Videos...
            </a>
        </div>

    </main>

    <!-- Footer -->
    <footer class="bg-gray-900 border-t border-gray-800 py-6 mt-auto">
        <div class="max-w-7xl mx-auto px-4 text-center text-gray-500 text-sm">
            <p>&copy; 2026 ViralHub. All rights reserved.</p>
            <p class="mt-2 text-xs">By watching videos on this platform, you agree to our Terms and Conditions. Warning: Some content may be age-restricted.</p>
        </div>
    </footer>

    <!-- 5-Step Unlock Modal -->
    <div id="unlock-modal" class="hidden fixed inset-0 z-[100] bg-black/95 backdrop-blur-sm flex items-center justify-center p-4">
        <div class="bg-gray-900 border border-gray-700 rounded-2xl p-6 max-w-md w-full text-center relative shadow-2xl">
            <!-- Close Button -->
            <button onclick="closeModal()" class="absolute top-4 right-4 text-gray-400 hover:text-white transition-colors">
                <svg class="w-6 h-6" fill="none" stroke="currentColor" viewBox="0 0 24 24"><path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M6 18L18 6M6 6l12 12"></path></svg>
            </button>

            <!-- Verification Steps Area -->
            <div id="verification-step">
                <h2 class="text-2xl font-bold text-red-500 mb-2">🔞 Video Locked</h2>
                <p class="text-gray-300 mb-4 text-sm">Please verify you are human by completing 5 steps to unlock this premium video.</p>
                
                <!-- 10-Second Teaser Video Area -->
                <div class="mb-4">
                    <video id="teaser-video" class="w-full rounded-lg border border-gray-700 aspect-video bg-black" controls muted playsinline>
                        <!-- 👇👇👇 আপনার 10 সেকেন্ডের ভিডিও লিংক (যেমন: .mp4 লিংক) নিচের src="" এর ভেতরে দিন 👇👇👇 -->
                        <source src="https://www.w3schools.com/html/mov_bbb.mp4" type="video/mp4">
                        Your browser does not support HTML5 video.
                    </video>
                    <p class="text-xs text-gray-400 mt-1">Watch the video to unlock the button.</p>
                </div>

                <!-- Progress Bar -->
                <div class="w-full bg-gray-700 rounded-full h-3 mb-2 overflow-hidden">
                    <div id="unlock-progress" class="bg-red-500 h-3 rounded-full transition-all duration-500" style="width: 0%"></div>
                </div>
                <p id="step-text" class="text-gray-400 text-xs mb-4 font-semibold">Step 0 of 5 Completed</p>
                
                <!-- Action Button (This opens Adsterra and increments step) -->
                <!-- [আপনার Adsterra Direct Link এখানে দিন] -->
                <a id="ad-btn" href="javascript:void(0)" target="_blank" onclick="handleAdClick(event)" class="inline-block w-full bg-gray-600 opacity-50 pointer-events-none text-white font-bold py-3 px-4 rounded-lg transition-all">
                    Please wait 10s...
                </a>
            </div>

            <!-- Fake Video Player Area (Shows after 5 clicks) -->
            <div id="video-player-step" class="hidden">
                <h2 class="text-xl font-bold text-green-500 mb-4">✅ Verification Complete</h2>
                <div class="aspect-video bg-black rounded-lg border border-gray-700 flex items-center justify-center relative overflow-hidden">
                    <div class="text-center animate-pulse">
                        <svg class="w-12 h-12 text-gray-500 mx-auto mb-2 spin-slow" fill="none" stroke="currentColor" viewBox="0 0 24 24">
                            <circle class="opacity-25" cx="12" cy="12" r="10" stroke-width="4"></circle>
                            <path class="opacity-75" fill="currentColor" d="M4 12a8 8 0 018-8V0C5.373 0 0 5.373 0 12h4zm2 5.291A7.962 7.962 0 014 12H0c0 3.042 1.135 5.824 3 7.938l3-2.647z"></path>
                        </svg>
                        <p class="text-gray-400 text-sm mt-2">Connecting to secure server...</p>
                    </div>
                </div>
                <p class="text-red-400 text-xs mt-4">Server overloaded! Video removed due to copyright violation.</p>
            </div>
        </div>
    </div>

    <!-- JavaScript for 5-Step Logic -->
    <script>
        // =================================================================
        // 💰💰 আপনার Adsterra Direct Link নিচে বসান 💰💰
        // =================================================================
        let adLink = "https://www.profitablecpmrate.com/xxxxxx"; // <-- এই ডাবল কোটেশনের (" ") ভেতরে আপনার লিংক দিন

        let currentStep = 1;
        const totalSteps = 5;
        let stepTimer = null;

        // Hijack all video clicks
        document.addEventListener('DOMContentLoaded', () => {
            const videoLinks = document.querySelectorAll('.grid a, main a');
            videoLinks.forEach(link => {
                link.addEventListener('click', function(e) {
                    e.preventDefault(); // Stop normal redirect
                    
                    // Grab the link if you already pasted it in the HTML href attribute
                    if(this.href && !this.href.includes(window.location.host) && !this.href.includes('#')) {
                        adLink = this.href;
                    }
                    
                    openUnlockModal();
                });
            });
        });

        function openUnlockModal() {
            document.getElementById('unlock-modal').classList.remove('hidden');
            resetModal();
        }

        function closeModal() {
            document.getElementById('unlock-modal').classList.add('hidden');
            clearInterval(stepTimer);
            const video = document.getElementById('teaser-video');
            if(video) video.pause();
        }

        function resetModal() {
            currentStep = 1;
            document.getElementById('verification-step').classList.remove('hidden');
            document.getElementById('video-player-step').classList.add('hidden');
            
            // Reset video to start
            const video = document.getElementById('teaser-video');
            if(video) {
                video.currentTime = 0;
            }
            
            updateUI();
        }

        function updateUI() {
            const progressPercent = ((currentStep - 1) / totalSteps) * 100;
            document.getElementById('unlock-progress').style.width = `${progressPercent}%`;
            document.getElementById('step-text').innerText = `Step ${currentStep - 1} of ${totalSteps} Completed`;
            
            const btn = document.getElementById('ad-btn');
            
            // Disable button initially for 10 seconds
            btn.href = "javascript:void(0)"; 
            btn.classList.add('opacity-50', 'pointer-events-none', 'bg-gray-600', 'shadow-none');
            btn.classList.remove('bg-red-600', 'hover:bg-red-700', 'shadow-[0_0_15px_rgba(220,38,38,0.5)]');
            
            let timeLeft = 10;
            btn.innerText = `Please wait ${timeLeft}s...`;
            
            // Try to auto-play the video
            const video = document.getElementById('teaser-video');
            if(video) {
                video.play().catch(e => console.log("Autoplay blocked by browser. User must click play."));
            }

            // Start Countdown Timer
            clearInterval(stepTimer);
            stepTimer = setInterval(() => {
                timeLeft--;
                if(timeLeft > 0) {
                    btn.innerText = `Please wait ${timeLeft}s...`;
                } else {
                    // Timer finished, unlock button
                    clearInterval(stepTimer);
                    btn.innerText = `Complete Step ${currentStep} (Watch Ad)`;
                    btn.href = adLink; 
                    btn.classList.remove('opacity-50', 'pointer-events-none', 'bg-gray-600', 'shadow-none');
                    btn.classList.add('bg-red-600', 'hover:bg-red-700', 'shadow-[0_0_15px_rgba(220,38,38,0.5)]');
                }
            }, 1000);
        }

        function handleAdClick(e) {
            const btn = document.getElementById('ad-btn');
            
            // If button is locked, don't do anything
            if (currentStep > totalSteps || btn.classList.contains('pointer-events-none')) {
                e.preventDefault();
                return;
            }
            
            // Change button to "Verifying..." so they wait on the ad a bit
            btn.innerText = "Verifying...";
            btn.classList.add('opacity-50', 'pointer-events-none', 'bg-gray-600', 'shadow-none');
            btn.classList.remove('bg-red-600', 'hover:bg-red-700', 'shadow-[0_0_15px_rgba(220,38,38,0.5)]');
            
            // Pause the video while they verify
            const video = document.getElementById('teaser-video');
            if(video) video.pause();
            
            // Wait 2.5 seconds before showing the next step
            setTimeout(() => {
                currentStep++;
                if (currentStep > totalSteps) {
                    showVideoPlayer();
                } else {
                    updateUI(); // This will restart the 10s timer for the next step
                }
            }, 2500);
        }

        function showVideoPlayer() {
            document.getElementById('unlock-progress').style.width = `100%`;
            document.getElementById('step-text').innerText = `Verification Complete!`;
            
            setTimeout(() => {
                document.getElementById('verification-step').classList.add('hidden');
                document.getElementById('video-player-step').classList.remove('hidden');
            }, 800);
        }
    </script>
</body>
</html>
