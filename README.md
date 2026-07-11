# Zyntrox-Ai-
<!DOCTYPE html>
<html lang="en" class="dark">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Zyntrox AI - Build Anything. Instantly.</title>
    <script src="https://cdn.tailwindcss.com"></script>
    <script>
        tailwind.config = {
            darkMode: 'class',
            theme: {
                extend: {
                    colors: {
                        brandDark: '#121212',
                        brandBoxDark: '#1a1a1a',
                    }
                }
            }
        }
    </script>
    <script src="https://unpkg.com/lucide@latest"></script>
    <script src="https://checkout.razorpay.com/v1/checkout.js"></script>
</head>
<body class="bg-white text-black dark:bg-brandDark dark:text-white min-h-screen flex flex-col justify-between font-sans transition-colors duration-300">

    <header class="flex justify-between items-center p-6 max-w-7xl w-full mx-auto">
        <div class="flex items-center gap-2 text-xl font-bold tracking-tight">
            <i data-lucide="hexagon" class="text-indigo-600 dark:text-indigo-400 fill-indigo-100 dark:fill-indigo-950/50"></i>
            <span>Zyntrox AI</span>
        </div>
        <div class="flex items-center gap-4">
            <button id="themeToggle" class="p-2 rounded-full hover:bg-gray-100 dark:hover:bg-gray-800 transition">
                <i data-lucide="sun" class="hidden dark:block w-5 h-5"></i>
                <i data-lucide="moon" class="block dark:hidden w-5 h-5"></i>
            </button>
            <button class="p-2 rounded-full hover:bg-gray-100 dark:hover:bg-gray-800 transition">
                <i data-lucide="user" class="w-5 h-5"></i>
            </button>
        </div>
    </header>

    <main class="flex-1 flex flex-col items-center justify-center px-4 max-w-4xl w-full mx-auto -mt-12">
        
        <div class="text-center mb-8">
            <div class="inline-block p-4 mb-3">
                <i data-lucide="hexagon" class="w-16 h-16 text-indigo-600 dark:text-indigo-400 stroke-[1.5]"></i>
            </div>
            <h1 class="text-4xl font-extrabold tracking-tight mb-2">Zyntrox AI</h1>
            <p class="text-gray-500 dark:text-gray-400 text-sm tracking-wide">Build Anything. Instantly.</p>
        </div>

        <div class="w-full bg-gray-50 dark:bg-brandBoxDark border border-gray-200 dark:border-gray-800 rounded-2xl p-4 shadow-sm mb-8 max-w-2xl transition">
            <p class="text-xs text-gray-400 dark:text-gray-500 mb-2 font-medium">What do you want Zyntrox to build today?</p>
            <textarea id="promptInput" rows="3" class="w-full bg-transparent resize-none outline-none text-base placeholder-gray-400" placeholder="Type your idea here..."></textarea>
            <div class="flex justify-between items-center mt-3 pt-2 border-t border-gray-100 dark:border-gray-800/50">
                <button class="p-2 text-gray-400 hover:text-gray-600 dark:hover:text-gray-200 transition">
                    <i data-lucide="plus" class="w-5 h-5"></i>
                </button>
                <div class="flex items-center gap-2">
                    <button class="p-2 text-gray-400 hover:text-gray-600 dark:hover:text-gray-200 transition">
                        <i data-lucide="mic" class="w-5 h-5"></i>
                    </button>
                    <button onclick="openForm('Prompt AI')" class="bg-blue-600 hover:bg-blue-700 text-white p-2.5 rounded-full transition shadow-md">
                        <i data-lucide="arrow-right" class="w-5 h-5"></i>
                    </button>
                </div>
            </div>
        </div>

        <div class="grid grid-cols-2 sm:grid-cols-3 md:grid-cols-6 gap-3 w-full max-w-3xl px-2">
            <button onclick="openForm('Website Builder')" class="flex flex-col items-start p-4 bg-white dark:bg-transparent border border-gray-100 dark:border-gray-800/80 rounded-xl hover:border-indigo-500 dark:hover:border-indigo-400 text-left transition group">
                <i data-lucide="globe" class="w-5 h-5 text-blue-500 mb-4"></i>
                <span class="text-xs font-semibold text-gray-800 dark:text-gray-200 block">Website Builder</span>
            </button>

            <button onclick="openForm('AI Agent')" class="flex flex-col items-start p-4 bg-white dark:bg-transparent border border-gray-100 dark:border-gray-800/80 rounded-xl hover:border-indigo-500 dark:hover:border-indigo-400 text-left transition">
                <i data-lucide="bot" class="w-5 h-5 text-purple-500 mb-4"></i>
                <span class="text-xs font-semibold text-gray-800 dark:text-gray-200 block">AI Agent</span>
            </button>

            <button class="flex flex-col items-start p-4 bg-white dark:bg-transparent border border-gray-100 dark:border-gray-800/80 rounded-xl hover:border-indigo-500 dark:hover:border-indigo-400 text-left transition opacity-50 cursor-not-allowed">
                <i data-lucide="smartphone" class="w-5 h-5 text-emerald-500 mb-4"></i>
                <span class="text-xs font-semibold text-gray-800 dark:text-gray-200 block">Mobile App</span>
            </button>

            <button class="flex flex-col items-start p-4 bg-white dark:bg-transparent border border-gray-100 dark:border-gray-800/80 rounded-xl hover:border-indigo-500 dark:hover:border-indigo-400 text-left transition opacity-50 cursor-not-allowed">
                <i data-lucide="pen-tool" class="w-5 h-5 text-amber-500 mb-4"></i>
                <span class="text-xs font-semibold text-gray-800 dark:text-gray-200 block">Logo Designer</span>
            </button>

            <button class="flex flex-col items-start p-4 bg-white dark:bg-transparent border border-gray-100 dark:border-gray-800/80 rounded-xl hover:border-indigo-500 dark:hover:border-indigo-400 text-left transition opacity-50 cursor-not-allowed">
                <i data-lucide="bar-chart-3" class="w-5 h-5 text-rose-500 mb-4"></i>
                <span class="text-xs font-semibold text-gray-800 dark:text-gray-200 block">Dashboard</span>
            </button>

            <button class="flex flex-col items-start p-4 bg-white dark:bg-transparent border border-gray-100 dark:border-gray-800/80 rounded-xl hover:border-indigo-500 dark:hover:border-indigo-400 text-left transition opacity-50 cursor-not-allowed">
                <i data-lucide="shopping-cart" class="w-5 h-5 text-indigo-500 mb-4"></i>
                <span class="text-xs font-semibold text-gray-800 dark:text-gray-200 block">Ecommerce</span>
            </button>
        </div>
    </main>

    <footer class="flex justify-between items-center p-6 max-w-7xl w-full mx-auto text-[11px] text-gray-400 dark:text-gray-600">
        <button class="p-2 border border-gray-100 dark:border-gray-800 rounded-xl hover:bg-gray-50 dark:hover:bg-gray-800 transition">
            <i data-lucide="gift" class="w-4 h-4"></i>
        </button>
        <div>Powered by Zyntrox AI</div>
        <div class="w-8"></div>
    </footer>

    <div id="formModal" class="fixed inset-0 bg-black/60 backdrop-blur-sm hidden items-center justify-center p-4 z-50">
        <div class="bg-white dark:bg-brandBoxDark border border-gray-200 dark:border-gray-800 w-full max-w-md rounded-2xl p-6 shadow-2xl">
            <div class="flex justify-between items-center mb-4">
                <h3 id="modalTitle" class="text-lg font-bold">Setup Your Project</h3>
                <button onclick="closeModal()" class="text-gray-400 hover:text-gray-600 dark:hover:text-gray-200"><i data-lucide="x" class="w-5 h-5"></i></button>
            </div>
            <div class="space-y-4">
                <div>
                    <label class="block text-xs font-medium text-gray-400 mb-1">Business Name</label>
                    <input id="bizName" type="text" class="w-full bg-gray-50 dark:bg-brandDark border border-gray-200 dark:border-gray-800 rounded-xl p-3 outline-none focus:border-indigo-500 text-sm" placeholder="e.g. Sharma Electronics">
                </div>
                <div>
                    <label class="block text-xs font-medium text-gray-400 mb-1">Category</label>
                    <select id="bizCategory" class="w-full bg-gray-50 dark:bg-brandDark border border-gray-200 dark:border-gray-800 rounded-xl p-3 outline-none focus:border-indigo-500 text-sm dark:text-gray-300">
                        <option value="Website">Website (₹249/mo)</option>
                        <option value="AI Agent">AI Agent (₹499/mo)</option>
                    </select>
                </div>
                <div>
                    <label class="block text-xs font-medium text-gray-400 mb-1">Describe your requirement</label>
                    <textarea id="bizDesc" rows="2" class="w-full bg-gray-50 dark:bg-brandDark border border-gray-200 dark:border-gray-800 rounded-xl p-3 outline-none focus:border-indigo-500 text-sm" placeholder="What should the AI build for you?"></textarea>
                </div>
                <button onclick="triggerPaymentFlow()" class="w-full bg-indigo-600 hover:bg-indigo-700 text-white font-semibold p-3 rounded-xl transition shadow-lg mt-2 text-sm">
                    Generate & Go Live
                </button>
            </div>
        </div>
    </div>

    <script>
        // Icons Initialization
        lucide.createIcons();

        // Dark/Light Theme Switching
        const themeToggleBtn = document.getElementById('themeToggle');
        themeToggleBtn.addEventListener('click', () => {
            document.documentElement.classList.toggle('dark');
        });

        // Modal Controls
        const modal = document.getElementById('formModal');
        function openForm(type) {
            document.getElementById('modalTitle').innerText = `Configure ${type}`;
            const selectBox = document.getElementById('bizCategory');
            if(type === 'AI Agent') {
                selectBox.value = 'AI Agent';
            } else {
                selectBox.value = 'Website';
            }
            
            // Sync main prompt box input to description inside form if available
            const mainPromptValue = document.getElementById('promptInput').value;
            if(mainPromptValue) {
                document.getElementById('bizDesc').value = mainPromptValue;
            }
            
            modal.classList.remove('hidden');
            modal.classList.add('flex');
        }
        function closeModal() {
            modal.classList.add('hidden');
            modal.classList.remove('flex');
        }

        // Integrated Payment Flow (Razorpay Gateway)
        function triggerPaymentFlow() {
            const name = document.getElementById('bizName').value;
            const category = document.getElementById('bizCategory').value;
            
            if(!name) {
                alert('Please enter your business name, bro!');
                return;
            }

            closeModal();
            
            // Deciding amount based on selection
            let amountInPaise = category === 'AI Agent' ? 49900 : 24900; 
            let displayAmount = category === 'AI Agent' ? '₹499' : '₹249';

            alert(`🚀 Zyntrox AI is preparing your project...\nClick OK to open secure checkout for ${displayAmount}.`);

            // Razorpay Payment Window Configuration
            const options = {
                "key": "rzp_test_YOUR_KEY_HERE", // Test Key (Works in test environment)
                "amount": amountInPaise, 
                "currency": "INR",
                "name": "Zyntrox AI", 
                "description": `${name} - ${category} Subscription`,
                "image": "https://img.icons8.com/color/512/hexagon.png",
                "handler": function (response) {
                    // This triggers automatically when simulated payment succeeds
                    alert(`🎉 Payment Successful!\nPayment ID: ${response.razorpay_payment_id}\n\nZyntrox AI is pushing your "${name}" project live now!`);
                },
                "prefill": {
                    "name": "Zyntrox Customer",
                    "email": "customer@zyntrox.ai"
                },
                "theme": {
                    "color": "#6366f1" // Premium Brand Purple
                }
            };

            const rzp = new Razorpay(options);
            rzp.open();
        }
    </script>
</body>
</html>
