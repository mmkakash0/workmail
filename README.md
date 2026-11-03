<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Daily Web Hub | Your 100 Categories</title>
    <script src="https://cdn.tailwindcss.com"></script>
    <link href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.0.0/css/all.min.css" rel="stylesheet">
    <link href="https://fonts.googleapis.com/css2?family=Inter:wght@300;400;500;600;700&display=swap" rel="stylesheet">
    <style>
        body {
            font-family: 'Inter', sans-serif;
            background-color: #f3f4f6;
        }
        /* Custom Scrollbar */
        ::-webkit-scrollbar {
            width: 8px;
        }
        ::-webkit-scrollbar-track {
            background: #f1f1f1; 
        }
        ::-webkit-scrollbar-thumb {
            background: #c1c1c1; 
            border-radius: 4px;
        }
        ::-webkit-scrollbar-thumb:hover {
            background: #a8a8a8; 
        }
        .glass-effect {
            background: rgba(255, 255, 255, 0.85);
            backdrop-filter: blur(10px);
        }
    </style>
</head>
<body class="text-gray-800 flex h-screen overflow-hidden bg-gray-50">

    <!-- Sidebar (Categories) -->
    <aside class="w-64 bg-white shadow-xl h-full flex flex-col hidden md:flex z-20 transition-all duration-300">
        <div class="p-6 border-b border-gray-100 flex items-center gap-3">
            <div class="bg-indigo-600 text-white p-2 rounded-lg">
                <i class="fa-solid fa-globe text-xl"></i>
            </div>
            <h1 class="text-xl font-bold bg-clip-text text-transparent bg-gradient-to-r from-indigo-600 to-purple-600">Web Hub</h1>
        </div>
        
        <div class="p-4">
            <h2 class="text-xs font-semibold text-gray-400 uppercase tracking-wider mb-3">All Categories (100)</h2>
            <div class="relative">
                <input type="text" id="categorySearch" placeholder="Search category..." 
                    class="w-full pl-9 pr-3 py-2 bg-gray-100 border-none rounded-lg text-sm focus:ring-2 focus:ring-indigo-500 outline-none transition-all">
                <i class="fa-solid fa-search absolute left-3 top-2.5 text-gray-400 text-sm"></i>
            </div>
        </div>

        <div class="flex-1 overflow-y-auto p-4 pt-0 space-y-1" id="sidebarCategories">
            <!-- Sidebar categories will be injected here -->
        </div>
    </aside>

    <!-- Main Content -->
    <main class="flex-1 flex flex-col h-full relative overflow-hidden">
        
        <!-- Topbar -->
        <header class="glass-effect shadow-sm z-10 border-b border-gray-100 p-4 md:p-6 flex justify-between items-center">
            <div class="flex items-center gap-4 w-full max-w-2xl">
                <button id="mobileMenuBtn" class="md:hidden text-gray-600 hover:text-indigo-600 focus:outline-none">
                    <i class="fa-solid fa-bars text-2xl"></i>
                </button>
                <div class="relative w-full">
                    <input type="text" id="globalSearch" placeholder="Search any website or category..." 
                        class="w-full pl-12 pr-4 py-3 bg-white border border-gray-200 rounded-xl text-base shadow-sm focus:ring-2 focus:ring-indigo-500 focus:border-transparent outline-none transition-all w-full">
                    <i class="fa-solid fa-magnifying-glass absolute left-4 top-3.5 text-gray-400 text-lg"></i>
                </div>
            </div>
            <div class="hidden sm:flex items-center gap-4 text-sm font-medium text-gray-500">
                <span><i class="fa-regular fa-clock mr-1"></i> <span id="timeDisplay"></span></span>
            </div>
        </header>

        <!-- Dynamic Grid Content -->
        <div class="flex-1 overflow-y-auto p-6 md:p-8" id="mainContainer">
            <!-- Website Cards will be injected here -->
        </div>
        
    </main>

    <!-- Mobile Sidebar Overlay -->
    <div id="mobileOverlay" class="fixed inset-0 bg-black/50 z-30 hidden md:hidden"></div>

    <script>
        // Database of 100 Categories (Mix of Real data & Programmatically Generated for fullness)
        const baseCategories = [
            { name: "Search Engines", icon: "fa-magnifying-glass", links: [
                { name: "Google", url: "https://google.com", desc: "Primary search engine" },
                { name: "Bing", url: "https://bing.com", desc: "Microsoft search" },
                { name: "DuckDuckGo", url: "https://duckduckgo.com", desc: "Privacy focused" }
            ]},
            { name: "Social Media", icon: "fa-hashtag", links: [
                { name: "Facebook", url: "https://facebook.com", desc: "Connect with friends" },
                { name: "X (Twitter)", url: "https://twitter.com", desc: "Microblogging" },
                { name: "Instagram", url: "https://instagram.com", desc: "Photo sharing" },
                { name: "LinkedIn", url: "https://linkedin.com", desc: "Professional network" }
            ]},
            { name: "Video Streaming", icon: "fa-play", links: [
                { name: "YouTube", url: "https://youtube.com", desc: "Video sharing" },
                { name: "Netflix", url: "https://netflix.com", desc: "Movies & TV" },
                { name: "Chorki", url: "https://chorki.com", desc: "Bangla entertainment" }
            ]},
            { name: "AI Tools", icon: "fa-robot", links: [
                { name: "ChatGPT", url: "https://chat.openai.com", desc: "OpenAI Chatbot" },
                { name: "Gemini", url: "https://gemini.google.com", desc: "Google AI" },
                { name: "Claude", url: "https://claude.ai", desc: "Anthropic AI" }
            ]},
            { name: "Email Services", icon: "fa-envelope", links: [
                { name: "Gmail", url: "https://mail.google.com", desc: "Google Mail" },
                { name: "Outlook", url: "https://outlook.com", desc: "Microsoft Mail" },
                { name: "ProtonMail", url: "https://proton.me", desc: "Secure Email" }
            ]},
            { name: "News (Bangladesh)", icon: "fa-newspaper", links: [
                { name: "Prothom Alo", url: "https://prothomalo.com", desc: "Daily newspaper" },
                { name: "The Daily Star", url: "https://thedailystar.net", desc: "English daily" },
                { name: "Somoy News", url: "https://somoynews.tv", desc: "News portal" }
            ]},
            { name: "E-Commerce (BD)", icon: "fa-cart-shopping", links: [
                { name: "Daraz", url: "https://daraz.com.bd", desc: "Online shopping" },
                { name: "Rokomari", url: "https://rokomari.com", desc: "Books & more" },
                { name: "Chaldal", url: "https://chaldal.com", desc: "Grocery delivery" }
            ]},
            { name: "Web Development", icon: "fa-code", links: [
                { name: "GitHub", url: "https://github.com", desc: "Code hosting" },
                { name: "CodePen", url: "https://codepen.io", desc: "Frontend playground" },
                { name: "Vercel", url: "https://vercel.com", desc: "Hosting platform" }
            ]},
            { name: "Design & UI", icon: "fa-pen-nib", links: [
                { name: "Figma", url: "https://figma.com", desc: "Design tool" },
                { name: "Canva", url: "https://canva.com", desc: "Graphic design" },
                { name: "Dribbble", url: "https://dribbble.com", desc: "Design inspiration" }
            ]},
            { name: "Cloud Storage", icon: "fa-cloud", links: [
                { name: "Google Drive", url: "https://drive.google.com", desc: "Cloud files" },
                { name: "Dropbox", url: "https://dropbox.com", desc: "File hosting" },
                { name: "OneDrive", url: "https://onedrive.live.com", desc: "Microsoft cloud" }
            ]},
            { name: "Education & Learning", icon: "fa-graduation-cap", links: [
                { name: "10 Minute School", url: "https://10minuteschool.com", desc: "BD EdTech" },
                { name: "Coursera", url: "https://coursera.org", desc: "Online courses" },
                { name: "Udemy", url: "https://udemy.com", desc: "Learning platform" }
            ]},
            { name: "Tech News", icon: "fa-microchip", links: [
                { name: "TechCrunch", url: "https://techcrunch.com", desc: "Startup news" },
                { name: "The Verge", url: "https://theverge.com", desc: "Tech & science" },
                { name: "Hacker News", url: "https://news.ycombinator.com", desc: "Dev news" }
            ]},
            { name: "Job Portals (BD)", icon: "fa-briefcase", links: [
                { name: "Bdjobs", url: "https://bdjobs.com", desc: "Jobs in Bangladesh" },
                { name: "LinkedIn Jobs", url: "https://linkedin.com/jobs", desc: "Global jobs" }
            ]},
            { name: "Freelancing", icon: "fa-laptop-house", links: [
                { name: "Upwork", url: "https://upwork.com", desc: "Freelance talent" },
                { name: "Fiverr", url: "https://fiverr.com", desc: "Freelance services" },
                { name: "Freelancer", url: "https://freelancer.com", desc: "Hire freelancers" }
            ]},
            { name: "Productivity", icon: "fa-check-double", links: [
                { name: "Notion", url: "https://notion.so", desc: "Workspace" },
                { name: "Trello", url: "https://trello.com", desc: "Project management" },
                { name: "Todoist", url: "https://todoist.com", desc: "To-do lists" }
            ]}
        ];

        // Let's programmatically expand the list to reach exactly 100 categories to meet user request
        const extraTopics = [
            "Finance", "Banking BD", "Cryptocurrency", "Stock Market", "Real Estate", 
            "Travel & Flights", "Hotels", "Food Delivery", "Recipes", "Health & Fitness",
            "Sports News", "Cricket", "Football", "Gaming", "PC Building",
            "Mobile Reviews", "Photography", "Stock Photos", "Fonts", "Icons",
            "Colors", "CSS Frameworks", "JS Libraries", "Web Hosting", "Domains",
            "Marketing", "SEO Tools", "Analytics", "Music Streaming", "Podcasts",
            "Audiobooks", "E-Books", "Comics", "Anime", "Movies Database",
            "Ticket Booking", "Event Management", "Government BD", "NID Services", "Passport BD",
            "Visa Information", "Weather", "Maps & Navigation", "Translation", "Dictionaries",
            "Encyclopedia", "Math Tools", "Science", "History", "Art Galleries",
            "Museums", "DIY & Crafts", "Gardening", "Pet Care", "Automotive",
            "Car Reviews", "Motorcycles", "Fashion", "Beauty", "Cosmetics",
            "Watches", "Jewelry", "Kids & Baby", "Toys", "Gifts",
            "Wedding Planning", "Astrology", "Religion", "Charity", "Volunteering",
            "Cybersecurity", "VPN Services", "Password Managers", "Antivirus", "Open Source",
            "Linux", "Windows", "MacOS", "Android", "iOS",
            "App Stores", "Browser Extensions", "Data Science", "Machine Learning", "IoT"
        ];

        const allCategories = [...baseCategories];
        const iconList = ["fa-star", "fa-bolt", "fa-leaf", "fa-fire", "fa-heart", "fa-gem", "fa-cube", "fa-compass"];

        extraTopics.forEach((topic, index) => {
            if(allCategories.length < 100) {
                allCategories.push({
                    name: topic,
                    icon: iconList[index % iconList.length],
                    links: [
                        { name: `Best ${topic} Sites`, url: `https://www.google.com/search?q=best+${encodeURIComponent(topic)}+websites`, desc: `Search portals for ${topic}` },
                        { name: `${topic} Resources`, url: `https://www.google.com/search?q=${encodeURIComponent(topic)}+resources+online`, desc: `Top resources for ${topic}` }
                    ]
                });
            }
        });

        // Add IDs for reference
        allCategories.forEach((cat, idx) => cat.id = `cat-${idx}`);

        // DOM Elements
        const sidebarCategories = document.getElementById('sidebarCategories');
        const mainContainer = document.getElementById('mainContainer');
        const globalSearch = document.getElementById('globalSearch');
        const categorySearch = document.getElementById('categorySearch');
        const timeDisplay = document.getElementById('timeDisplay');

        // Render Sidebar
        function renderSidebar(categories) {
            sidebarCategories.innerHTML = '';
            categories.forEach(cat => {
                const btn = document.createElement('button');
                btn.className = 'w-full flex items-center gap-3 px-3 py-2 rounded-lg text-sm text-gray-600 hover:bg-indigo-50 hover:text-indigo-700 transition-colors text-left';
                btn.onclick = () => scrollToCategory(cat.id);
                btn.innerHTML = `
                    <i class="fa-solid ${cat.icon} w-5 text-center opacity-70"></i>
                    <span class="truncate font-medium">${cat.name}</span>
                `;
                sidebarCategories.appendChild(btn);
            });
        }

        // Render Main Content
        function renderMain(categories) {
            mainContainer.innerHTML = '';
            categories.forEach(cat => {
                const section = document.createElement('div');
                section.id = cat.id;
                section.className = 'mb-10 category-section scroll-mt-24';
                
                let linksHTML = cat.links.map(link => `
                    <a href="${link.url}" target="_blank" class="group bg-white border border-gray-100 p-4 rounded-xl hover:shadow-lg hover:border-indigo-100 transition-all duration-300 flex items-start gap-4">
                        <div class="bg-gray-50 p-3 rounded-lg group-hover:bg-indigo-50 transition-colors">
                            <img src="https://www.google.com/s2/favicons?domain=${link.url}&sz=32" alt="" class="w-6 h-6 object-contain rounded" onerror="this.src='https://placehold.co/32x32/e2e8f0/64748b?text=W'">
                        </div>
                        <div class="flex-1 min-w-0">
                            <h3 class="text-sm font-semibold text-gray-800 group-hover:text-indigo-600 truncate">${link.name}</h3>
                            <p class="text-xs text-gray-500 mt-1 truncate">${link.desc}</p>
                        </div>
                        <i class="fa-solid fa-arrow-up-right-from-square text-gray-300 group-hover:text-indigo-400 text-xs mt-1"></i>
                    </a>
                `).join('');

                section.innerHTML = `
                    <div class="flex items-center gap-3 mb-5 border-b border-gray-200 pb-2">
                        <i class="fa-solid ${cat.icon} text-indigo-500 text-lg"></i>
                        <h2 class="text-xl font-bold text-gray-800">${cat.name}</h2>
                        <span class="ml-auto text-xs bg-gray-200 text-gray-600 px-2 py-1 rounded-full">${cat.links.length} Sites</span>
                    </div>
                    <div class="grid grid-cols-1 sm:grid-cols-2 lg:grid-cols-3 xl:grid-cols-4 gap-4">
                        ${linksHTML}
                    </div>
                `;
                mainContainer.appendChild(section);
            });
        }

        // Search Functionality
        globalSearch.addEventListener('input', (e) => {
            const term = e.target.value.toLowerCase();
            const filtered = allCategories.map(cat => {
                const matchCat = cat.name.toLowerCase().includes(term);
                const matchedLinks = cat.links.filter(l => l.name.toLowerCase().includes(term) || l.desc.toLowerCase().includes(term));
                
                if (matchCat || matchedLinks.length > 0) {
                    return {
                        ...cat,
                        links: matchCat ? cat.links : matchedLinks // If category matches, show all links, else show matched links
                    };
                }
                return null;
            }).filter(Boolean);
            
            renderMain(filtered);
        });

        categorySearch.addEventListener('input', (e) => {
            const term = e.target.value.toLowerCase();
            const filtered = allCategories.filter(cat => cat.name.toLowerCase().includes(term));
            renderSidebar(filtered);
        });

        // Smooth Scroll & Auto-close Mobile Menu
        function scrollToCategory(id) {
            const el = document.getElementById(id);
            if(el) {
                el.scrollIntoView({ behavior: 'smooth' });
            }
            
            // Auto close mobile sidebar if it is open
            if (window.innerWidth < 768) {
                const sidebar = document.querySelector('aside');
                const mobileOverlay = document.getElementById('mobileOverlay');
                if (!sidebar.classList.contains('hidden')) {
                    sidebar.classList.add('hidden');
                    sidebar.classList.remove('absolute');
                    sidebar.classList.remove('z-40');
                    mobileOverlay.classList.add('hidden');
                }
            }
        }

        // Clock Update
        function updateTime() {
            const now = new Date();
            timeDisplay.textContent = now.toLocaleTimeString('en-US', { hour: '2-digit', minute: '2-digit' });
        }
        setInterval(updateTime, 1000);
        updateTime();

        // Mobile Menu Logic
        const mobileMenuBtn = document.getElementById('mobileMenuBtn');
        const sidebar = document.querySelector('aside');
        const mobileOverlay = document.getElementById('mobileOverlay');

        mobileMenuBtn.addEventListener('click', () => {
            sidebar.classList.toggle('hidden');
            sidebar.classList.toggle('absolute');
            sidebar.classList.toggle('z-40');
            mobileOverlay.classList.toggle('hidden');
        });

        mobileOverlay.addEventListener('click', () => {
            sidebar.classList.add('hidden');
            sidebar.classList.remove('absolute');
            sidebar.classList.remove('z-40');
            mobileOverlay.classList.add('hidden');
        });

        // Initial Render
        renderSidebar(allCategories);
        renderMain(allCategories);

    </script>
</body>
</html>
