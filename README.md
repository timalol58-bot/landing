<!DOCTYPE html>
<html lang="uk">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Заявка на автоматизацію n8n</title>
    
    <!-- Підключення шрифту Montserrat -->
    <link rel="preconnect" href="https://fonts.googleapis.com">
    <link rel="preconnect" href="https://fonts.gstatic.com" crossorigin>
    <link href="https://fonts.googleapis.com/css2?family=Montserrat:wght@300;400;500;600;700;800&display=swap" rel="stylesheet">
    
    <!-- Підключення Tailwind CSS -->
    <script src="https://cdn.tailwindcss.com"></script>
    
    <!-- Налаштування -->
    <script>
        tailwind.config = {
            theme: {
                extend: {
                    fontFamily: {
                        sans: ['Montserrat', 'sans-serif'],
                    },
                    colors: {
                        brand: {
                            light: '#FF8787',
                            DEFAULT: '#EA4C62', // Більш насичений n8n колір
                            dark: '#C03448'
                        },
                        telegram: '#229ED9', // Офіційний колір Telegram
                        telegramHover: '#1f94cc'
                    },
                    animation: {
                        'blob': 'blob 7s infinite',
                        'fade-in-up': 'fadeInUp 0.8s ease-out forwards',
                        'shimmer': 'shimmer 2s infinite',
                    },
                    keyframes: {
                        blob: {
                            '0%': { transform: 'translate(0px, 0px) scale(1)' },
                            '33%': { transform: 'translate(30px, -50px) scale(1.1)' },
                            '66%': { transform: 'translate(-20px, 20px) scale(0.9)' },
                            '100%': { transform: 'translate(0px, 0px) scale(1)' },
                        },
                        fadeInUp: {
                            '0%': { opacity: '0', transform: 'translateY(20px)' },
                            '100%': { opacity: '1', transform: 'translateY(0)' },
                        },
                        shimmer: {
                            '0%': { transform: 'translateX(-100%)' },
                            '100%': { transform: 'translateX(100%)' }
                        }
                    }
                }
            }
        }
    </script>
    <style>
        body {
            /* Живий фон */
            background-color: #f3f4f6;
            overflow-x: hidden;
        }
        
        .glass-card {
            background: rgba(255, 255, 255, 0.7);
            backdrop-filter: blur(20px);
            -webkit-backdrop-filter: blur(20px);
            border: 1px solid rgba(255, 255, 255, 0.5);
            box-shadow: 0 20px 40px -10px rgba(0, 0, 0, 0.1);
        }

        .input-group:focus-within label {
            color: #EA4C62;
        }
        
        .input-group:focus-within svg {
            color: #EA4C62;
        }

        /* Анімовані кулі на фоні */
        .bg-shape {
            position: absolute;
            filter: blur(50px);
            z-index: -1;
            animation: blob 7s infinite;
        }
    </style>
</head>
<body class="min-h-screen flex items-center justify-center p-4 relative text-gray-800">

    <!-- Фонова анімація (яскраві плями) -->
    <div class="fixed top-0 left-0 w-full h-full overflow-hidden pointer-events-none z-0">
        <div class="bg-shape bg-purple-300 w-96 h-96 rounded-full mix-blend-multiply opacity-70 -top-20 -left-20"></div>
        <div class="bg-shape bg-yellow-300 w-96 h-96 rounded-full mix-blend-multiply opacity-70 top-40 right-10 animation-delay-2000"></div>
        <div class="bg-shape bg-brand-light w-96 h-96 rounded-full mix-blend-multiply opacity-70 -bottom-32 left-20 animation-delay-4000"></div>
    </div>

    <!-- Основна картка -->
    <div class="glass-card w-full max-w-lg rounded-3xl p-8 md:p-12 relative z-10 animate-fade-in-up">
        
        <!-- Заголовок -->
        <div class="text-center mb-10">
            <div class="inline-block p-3 rounded-2xl bg-gradient-to-tr from-brand-light to-brand text-white mb-4 shadow-lg shadow-brand/30">
                <svg xmlns="http://www.w3.org/2000/svg" class="h-8 w-8" fill="none" viewBox="0 0 24 24" stroke="currentColor">
                    <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M13 10V3L4 14h7v7l9-11h-7z" />
                </svg>
            </div>
            <h1 class="text-3xl md:text-4xl font-bold bg-clip-text text-transparent bg-gradient-to-r from-gray-900 to-gray-600 mb-2">n8n Automation</h1>
            <p class="text-gray-500 font-medium">Твоя автоматизація починається тут</p>
        </div>

        <!-- КНОПКА TELEGRAM -->
        <a href="https://t.me/landosikmykhal_bot" target="_blank" class="block w-full mb-8 transform transition-all hover:-translate-y-1 hover:shadow-lg group relative overflow-hidden rounded-xl">
            <div class="bg-telegram hover:bg-telegramHover text-white p-4 flex items-center justify-center gap-4 transition-colors relative z-10">
                
                <!-- Анімований блік -->
                <div class="absolute inset-0 bg-gradient-to-r from-transparent via-white/20 to-transparent -translate-x-full group-hover:animate-shimmer z-0"></div>

                <!-- Іконка Telegram -->
                <div class="bg-white/20 p-2 rounded-full relative z-10">
                    <svg xmlns="http://www.w3.org/2000/svg" class="h-6 w-6 fill-current" viewBox="0 0 24 24">
                        <path d="M11.944 0A12 12 0 0 0 0 12a12 12 0 0 0 12 12 12 12 0 0 0 12-12A12 12 0 0 0 11.944 0zm4.962 7.224c.1-.002.321.023.465.14a.506.506 0 0 1 .171.325c.016.093.036.306.02.472-.18 1.898-.962 6.502-1.36 8.627-.168.9-.499 1.201-.82 1.23-.696.065-1.225-.46-1.9-.902-1.056-.693-1.653-1.124-2.678-1.8-1.185-.78-.417-1.21.258-1.91.177-.184 3.247-2.977 3.307-3.23.007-.032.014-.15-.056-.212s-.174-.041-.249-.024c-.106.024-1.793 1.14-5.061 3.345-.48.33-.913.49-1.302.48-.428-.008-1.252-.241-1.865-.44-.752-.245-1.349-.374-1.297-.789.027-.216.325-.437.893-.663 3.498-1.524 5.83-2.529 6.998-3.014 3.332-1.386 4.025-1.627 4.476-1.635z"/>
                    </svg>
                </div>
                
                <div class="text-left relative z-10">
                    <p class="text-[10px] font-bold text-blue-100 uppercase tracking-widest opacity-80">Обов'язково</p>
                    <p class="font-bold text-lg leading-tight">Натиснути START у боті</p>
                </div>
                
                <!-- Стрілка -->
                <svg xmlns="http://www.w3.org/2000/svg" class="h-5 w-5 ml-auto opacity-70 group-hover:translate-x-1 transition-transform relative z-10" fill="none" viewBox="0 0 24 24" stroke="currentColor">
                    <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M13 7l5 5m0 0l-5 5m5-5H6" />
                </svg>
            </div>
        </a>

        <!-- Форма -->
        <form id="consultationForm" class="space-y-6">
            
            <!-- Прізвище та Ім'я -->
            <div class="input-group">
                <label for="fullName" class="block text-xs font-bold text-gray-500 uppercase tracking-wider mb-2 transition-colors">Прізвище та Ім'я</label>
                <div class="relative">
                    <div class="absolute inset-y-0 left-0 pl-4 flex items-center pointer-events-none transition-colors text-gray-400">
                        <svg class="h-5 w-5" fill="none" viewBox="0 0 24 24" stroke="currentColor">
                            <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M16 7a4 4 0 11-8 0 4 4 0 018 0zM12 14a7 7 0 00-7 7h14a7 7 0 00-7-7z" />
                        </svg>
                    </div>
                    <input type="text" id="fullName" name="fullName" required placeholder="Ілон Маск" 
                        class="w-full pl-11 pr-4 py-4 rounded-xl border border-gray-200 bg-white/50 focus:bg-white text-gray-800 font-medium placeholder-gray-400 focus:outline-none focus:border-brand focus:ring-4 focus:ring-brand/10 transition-all shadow-sm">
                </div>
            </div>

            <!-- Telegram ID -->
            <div class="input-group">
                <label for="telegramId" class="block text-xs font-bold text-gray-500 uppercase tracking-wider mb-2 transition-colors">Telegram ID</label>
                <div class="relative">
                    <div class="absolute inset-y-0 left-0 pl-4 flex items-center pointer-events-none transition-colors text-gray-400">
                        <svg class="h-5 w-5" fill="none" viewBox="0 0 24 24" stroke="currentColor">
                            <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M12 18h.01M8 21h8a2 2 0 002-2V5a2 2 0 00-2-2H8a2 2 0 00-2 2v14a2 2 0 002 2z" />
                        </svg>
                    </div>
                    <input type="text" id="telegramId" name="telegramId" required placeholder="123456789" 
                        class="w-full pl-11 pr-4 py-4 rounded-xl border border-gray-200 bg-white/50 focus:bg-white text-gray-800 font-medium placeholder-gray-400 focus:outline-none focus:border-brand focus:ring-4 focus:ring-brand/10 transition-all shadow-sm">
                </div>
            </div>

            <!-- Терміновість -->
            <div>
                <label class="block text-xs font-bold text-gray-500 uppercase tracking-wider mb-3">Терміновість</label>
                <div class="grid grid-cols-3 gap-3">
                    <label class="cursor-pointer relative">
                        <input type="radio" name="urgency" value="low" class="peer sr-only" required>
                        <div class="p-3 rounded-xl border border-gray-200 bg-white/50 text-center hover:bg-white peer-checked:bg-green-50 peer-checked:border-green-500 peer-checked:text-green-700 transition-all h-full flex flex-col items-center justify-center gap-1">
                            <span class="text-2xl">☕</span>
                            <span class="text-xs font-bold">Не горить</span>
                        </div>
                    </label>
                    <label class="cursor-pointer relative">
                        <input type="radio" name="urgency" value="medium" class="peer sr-only">
                        <div class="p-3 rounded-xl border border-gray-200 bg-white/50 text-center hover:bg-white peer-checked:bg-blue-50 peer-checked:border-blue-500 peer-checked:text-blue-700 transition-all h-full flex flex-col items-center justify-center gap-1">
                            <span class="text-2xl">🚀</span>
                            <span class="text-xs font-bold">Скоро</span>
                        </div>
                    </label>
                    <label class="cursor-pointer relative">
                        <input type="radio" name="urgency" value="high" class="peer sr-only">
                        <div class="p-3 rounded-xl border border-gray-200 bg-white/50 text-center hover:bg-white peer-checked:bg-brand/10 peer-checked:border-brand peer-checked:text-brand transition-all h-full flex flex-col items-center justify-center gap-1">
                            <span class="text-2xl">🔥</span>
                            <span class="text-xs font-bold">АСАП</span>
                        </div>
                    </label>
                </div>
            </div>

            <!-- Опис задачі -->
            <div class="input-group">
                <label for="description" class="block text-xs font-bold text-gray-500 uppercase tracking-wider mb-2 transition-colors">Що автоматизуємо?</label>
                <textarea id="description" name="description" rows="4" required placeholder="Опишіть вашу ідею..." 
                    class="w-full p-4 rounded-xl border border-gray-200 bg-white/50 focus:bg-white text-gray-800 font-medium placeholder-gray-400 focus:outline-none focus:border-brand focus:ring-4 focus:ring-brand/10 transition-all shadow-sm resize-none"></textarea>
            </div>

            <!-- Кнопка відправки -->
            <button type="submit" id="submitBtn" class="w-full bg-gradient-to-r from-brand to-brand-light hover:from-brand-dark hover:to-brand text-white font-bold py-4 rounded-xl shadow-lg shadow-brand/30 transform hover:-translate-y-1 hover:shadow-2xl transition-all duration-300 flex items-center justify-center gap-2 group">
                <span class="group-hover:scale-105 transition-transform">Відправити заявку</span>
                <svg xmlns="http://www.w3.org/2000/svg" class="h-5 w-5 group-hover:translate-x-1 transition-transform" fill="none" viewBox="0 0 24 24" stroke="currentColor">
                    <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M14 5l7 7m0 0l-7 7m7-7H3" />
                </svg>
            </button>
        </form>

        <!-- Повідомлення про успіх -->
        <div id="successMessage" class="hidden text-center py-10 animate-fade-in-up">
            <div class="w-20 h-20 bg-green-100 rounded-full flex items-center justify-center mx-auto mb-6 shadow-green-200 shadow-lg">
                <svg class="w-10 h-10 text-green-500" fill="none" stroke="currentColor" viewBox="0 0 24 24"><path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M5 13l4 4L19 7"></path></svg>
            </div>
            <h3 class="text-2xl font-bold text-gray-800 mb-2">Заявку прийнято!</h3>
            <p class="text-gray-600 mb-8">Ми вже обробляємо ваш запит. <br>Перевірте Telegram — бот вже стукає до вас.</p>
            <button onclick="location.reload()" class="text-brand font-bold hover:text-brand-dark transition-colors flex items-center justify-center gap-2 mx-auto">
                <svg xmlns="http://www.w3.org/2000/svg" class="h-4 w-4" fill="none" viewBox="0 0 24 24" stroke="currentColor">
                    <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M4 4v5h.582m15.356 2A8.001 8.001 0 004.582 9m0 0H9m11 11v-5h-.581m0 0a8.003 8.003 0 01-15.357-2m15.357 2H15" />
                </svg>
                Створити нову
            </button>
        </div>

    </div>

    <!-- Футер -->
    <div class="absolute bottom-4 text-center w-full z-10 pointer-events-none">
        <p class="text-xs text-gray-400 font-medium tracking-wide">POWERED BY N8N</p>
    </div>

    <script>
        const form = document.getElementById('consultationForm');
        const submitBtn = document.getElementById('submitBtn');
        const successMessage = document.getElementById('successMessage');
        const webhookUrl = 'https://timaloln8n.site/webhook/consultation-form';

        form.addEventListener('submit', function(e) {
            e.preventDefault();

            // Збираємо дані
            const urgency = document.querySelector('input[name="urgency"]:checked')?.value || 'low';
            const formData = {
                name: document.getElementById('fullName').value,
                telegramId: document.getElementById('telegramId').value,
                urgency: urgency,
                description: document.getElementById('description').value,
                date: new Date().toLocaleString('uk-UA')
            };

            // Анімація завантаження
            const btnContent = submitBtn.innerHTML;
            submitBtn.disabled = true;
            submitBtn.innerHTML = `
                <svg class="animate-spin -ml-1 mr-3 h-5 w-5 text-white" xmlns="http://www.w3.org/2000/svg" fill="none" viewBox="0 0 24 24">
                    <circle class="opacity-25" cx="12" cy="12" r="10" stroke="currentColor" stroke-width="4"></circle>
                    <path class="opacity-75" fill="currentColor" d="M4 12a8 8 0 018-8V0C5.373 0 0 5.373 0 12h4zm2 5.291A7.962 7.962 0 014 12H0c0 3.042 1.135 5.824 3 7.938l3-2.647z"></path>
                </svg>
                Відправка...
            `;
            submitBtn.classList.add('opacity-80', 'cursor-not-allowed');

            // Відправка
            fetch(webhookUrl, {
                method: 'POST',
                headers: { 'Content-Type': 'application/json' },
                body: JSON.stringify(formData)
            })
            .then(response => {
                if (!response.ok) {
                    throw new Error('Network response was not ok');
                }
                showSuccess();
            })
            .catch(error => {
                console.error('Помилка відправки:', error);
                alert('Помилка! n8n не приймає дані. Перевірте налаштування CORS в n8n Webhook node (Allowed Origins: *).');
            })
            .finally(() => {
                submitBtn.disabled = false;
                submitBtn.innerHTML = btnContent;
                submitBtn.classList.remove('opacity-80', 'cursor-not-allowed');
            });
        });

        function showSuccess() {
            form.style.display = 'none';
            successMessage.classList.remove('hidden');
        }
    </script>
</body>
</html>
