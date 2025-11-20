# Rey-Ivy-Rose
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Rey Ivy Rose | Official Store</title>
    <script src="https://cdn.tailwindcss.com"></script>
    <link href="https://fonts.googleapis.com/css2?family=Cinzel:wght@400;700&family=Playfair+Display:ital,wght@0,400;0,700;1,400&family=Montserrat:wght@300;400;600&display=swap" rel="stylesheet">
    <!-- Lucide Icons -->
    <script src="https://unpkg.com/lucide@latest"></script>
    <style>
        :root {
            --deep-blue: #02041a;
            --rose-blue: #1e2a4a;
            --accent-blue: #4f6d96;
            --text-silver: #e0e6ed;
        }
        
        body {
            background-color: var(--deep-blue);
            color: var(--text-silver);
            font-family: 'Montserrat', sans-serif;
            overflow-x: hidden;
        }

        h1, h2, h3 {
            font-family: 'Cinzel', serif;
        }

        .fancy-font {
            font-family: 'Playfair Display', serif;
            font-style: italic;
        }

        /* Canvas for Particles */
        #particle-canvas {
            position: fixed;
            top: 0;
            left: 0;
            width: 100%;
            height: 100%;
            z-index: -1;
            pointer-events: none;
        }

        /* Glassmorphism */
        .glass-panel {
            background: rgba(30, 42, 74, 0.4);
            backdrop-filter: blur(12px);
            -webkit-backdrop-filter: blur(12px);
            border: 1px solid rgba(255, 255, 255, 0.1);
        }

        .product-card {
            transition: transform 0.4s ease, box-shadow 0.4s ease;
        }

        .product-card:hover {
            transform: translateY(-10px);
            box-shadow: 0 20px 40px rgba(0, 10, 30, 0.6);
        }

        .btn-fancy {
            position: relative;
            overflow: hidden;
            transition: all 0.3s ease;
        }
        
        .btn-fancy::after {
            content: '';
            position: absolute;
            top: 0;
            left: -100%;
            width: 100%;
            height: 100%;
            background: linear-gradient(90deg, transparent, rgba(255,255,255,0.2), transparent);
            transition: 0.5s;
        }
        
        .btn-fancy:hover::after {
            left: 100%;
        }

        /* Animations */
        @keyframes fadeIn {
            from { opacity: 0; transform: translateY(20px); }
            to { opacity: 1; transform: translateY(0); }
        }

        .animate-fade-in {
            animation: fadeIn 1s ease-out forwards;
        }

        /* Custom Scrollbar */
        ::-webkit-scrollbar {
            width: 8px;
        }
        ::-webkit-scrollbar-track {
            background: var(--deep-blue);
        }
        ::-webkit-scrollbar-thumb {
            background: var(--accent-blue);
            border-radius: 4px;
        }

        /* Modal Transition */
        .modal {
            transition: opacity 0.3s ease, visibility 0.3s ease;
            opacity: 0;
            visibility: hidden;
        }
        .modal.active {
            opacity: 1;
            visibility: visible;
        }
    </style>
</head>
<body class="min-h-screen flex flex-col relative">

    <!-- Particle Background -->
    <canvas id="particle-canvas"></canvas>

    <!-- Navigation -->
    <nav class="fixed w-full z-50 px-6 py-4 glass-panel">
        <div class="max-w-7xl mx-auto flex justify-between items-center">
            <div class="text-2xl md:text-3xl font-bold tracking-widest text-blue-200">REY IVY ROSE</div>
            <button onclick="openCart()" class="relative p-2 hover:text-blue-300 transition">
                <i data-lucide="shopping-bag" class="w-8 h-8"></i>
                <span id="cart-count" class="absolute top-0 right-0 bg-blue-600 text-xs rounded-full w-5 h-5 flex items-center justify-center opacity-0 transition-opacity">0</span>
            </button>
        </div>
    </nav>

    <!-- Hero Section -->
    <header class="pt-32 pb-16 px-6 text-center relative">
        <div class="animate-fade-in">
            <h1 class="text-5xl md:text-7xl lg:text-9xl mb-4 text-transparent bg-clip-text bg-gradient-to-r from-blue-200 via-white to-blue-200 drop-shadow-lg">
                The Collection
            </h1>
            <p class="fancy-font text-xl md:text-3xl text-blue-300 mt-4">Fragile hearts wander our path ahead.</p>
        </div>
    </header>

    <!-- Products Section -->
    <main class="flex-grow container mx-auto px-4 py-12">
        <div class="grid md:grid-cols-2 gap-12 max-w-6xl mx-auto">
            
            <!-- Album 1: FRAGILE -->
            <div class="product-card glass-panel rounded-xl overflow-hidden p-6 animate-fade-in" style="animation-delay: 0.2s;">
                <div class="relative aspect-square rounded-lg overflow-hidden mb-6 group">
                    <!-- Using the car image for FRAGILE -->
                    <img src="WhatsApp Image 2025-11-20 at 7.38.38 PM.jpeg" 
                         alt="FRAGILE Album Cover" 
                         class="w-full h-full object-cover transform group-hover:scale-105 transition duration-700"
                         onerror="this.src='https://via.placeholder.com/800x800/1e2a4a/ffffff?text=FRAGILE+Album+Art'">
                    <div class="absolute inset-0 bg-black bg-opacity-0 group-hover:bg-opacity-30 transition duration-500"></div>
                </div>
                <h2 class="text-3xl md:text-4xl mb-2">FRAGILE</h2>
                <p class="text-blue-300 mb-6 fancy-font text-lg">The debut studio album.</p>
                
                <div class="space-y-4">
                    <div class="flex justify-between items-center border-b border-blue-800 pb-2">
                        <select id="format-fragile" class="bg-transparent border border-blue-700 rounded px-3 py-2 outline-none focus:border-blue-400 w-full mr-4">
                            <option value="Vinyl - $35.00" class="bg-gray-900">Standard Vinyl - $35.00</option>
                            <option value="CD - $15.00" class="bg-gray-900">Jewel Case CD - $15.00</option>
                            <option value="Cassette - $12.00" class="bg-gray-900">Blue Cassette - $12.00</option>
                        </select>
                    </div>
                    <button onclick="addToCart('FRAGILE', 'format-fragile', 'WhatsApp Image 2025-11-20 at 7.38.38 PM.jpeg')" 
                            class="btn-fancy w-full bg-blue-900 hover:bg-blue-800 text-white py-4 rounded uppercase tracking-widest font-bold">
                        Add to Cart
                    </button>
                </div>
            </div>

            <!-- Album 2: Our Path Ahead Of Us -->
            <div class="product-card glass-panel rounded-xl overflow-hidden p-6 animate-fade-in" style="animation-delay: 0.4s;">
                <div class="relative aspect-square rounded-lg overflow-hidden mb-6 group">
                    <!-- Using the woman image for Our Path -->
                    <img src="WhatsApp Image 2025-11-20 at 7.38.39 PM.jpeg" 
                         alt="Our Path Ahead Of Us Album Cover" 
                         class="w-full h-full object-cover transform group-hover:scale-105 transition duration-700"
                         onerror="this.src='https://via.placeholder.com/800x800/1e2a4a/ffffff?text=Our+Path+Album+Art'">
                    <div class="absolute inset-0 bg-black bg-opacity-0 group-hover:bg-opacity-30 transition duration-500"></div>
                </div>
                <h2 class="text-3xl md:text-4xl mb-2">Our Path Ahead Of Us</h2>
                <p class="text-blue-300 mb-6 fancy-font text-lg">The sophomore journey.</p>
                
                <div class="space-y-4">
                    <div class="flex justify-between items-center border-b border-blue-800 pb-2">
                        <select id="format-path" class="bg-transparent border border-blue-700 rounded px-3 py-2 outline-none focus:border-blue-400 w-full mr-4">
                            <option value="Vinyl - $35.00" class="bg-gray-900">Standard Vinyl - $35.00</option>
                            <option value="CD - $15.00" class="bg-gray-900">Jewel Case CD - $15.00</option>
                            <option value="Cassette - $12.00" class="bg-gray-900">Cobalt Cassette - $12.00</option>
                        </select>
                    </div>
                    <button onclick="addToCart('Our Path Ahead Of Us', 'format-path', 'WhatsApp Image 2025-11-20 at 7.38.39 PM.jpeg')" 
                            class="btn-fancy w-full bg-blue-900 hover:bg-blue-800 text-white py-4 rounded uppercase tracking-widest font-bold">
                        Add to Cart
                    </button>
                </div>
            </div>

        </div>
    </main>

    <!-- Footer -->
    <footer class="text-center py-10 text-blue-400 text-sm relative z-10">
        <div class="flex justify-center gap-6 mb-4">
            <i data-lucide="instagram" class="w-5 h-5 hover:text-white cursor-pointer"></i>
            <i data-lucide="twitter" class="w-5 h-5 hover:text-white cursor-pointer"></i>
            <i data-lucide="music-2" class="w-5 h-5 hover:text-white cursor-pointer"></i>
        </div>
        <p>&copy; 2025 Rey Ivy Rose. All Rights Reserved.</p>
    </footer>

    <!-- Cart Sidebar Modal -->
    <div id="cart-modal" class="modal fixed inset-0 z-[60] flex justify-end">
        <div class="absolute inset-0 bg-black bg-opacity-70 backdrop-blur-sm" onclick="closeCart()"></div>
        <div class="relative w-full max-w-md h-full bg-[#0a1124] border-l border-blue-900 p-6 flex flex-col shadow-2xl transform transition-transform duration-300 translate-x-full" id="cart-panel">
            <div class="flex justify-between items-center mb-8">
                <h2 class="text-2xl font-serif">Your Cart</h2>
                <button onclick="closeCart()" class="text-gray-400 hover:text-white">
                    <i data-lucide="x" class="w-6 h-6"></i>
                </button>
            </div>
            
            <div id="cart-items" class="flex-grow overflow-y-auto space-y-4">
                <!-- Cart items injected here -->
                <p class="text-center text-gray-500 mt-10 fancy-font">Your cart is empty, like a void...</p>
            </div>

            <div class="border-t border-blue-900 pt-6 mt-4">
                <div class="flex justify-between text-xl mb-6">
                    <span>Total</span>
                    <span id="cart-total">$0.00</span>
                </div>
                <button onclick="goToCheckout()" class="w-full bg-white text-black py-4 font-bold uppercase tracking-widest hover:bg-blue-100 transition">
                    Checkout
                </button>
            </div>
        </div>
    </div>

    <!-- Checkout Modal -->
    <div id="checkout-modal" class="modal fixed inset-0 z-[70] flex items-center justify-center p-4">
        <div class="absolute inset-0 bg-[#02041a] bg-opacity-95 backdrop-blur-md"></div>
        <div class="relative w-full max-w-2xl bg-[#0e1a35] border border-blue-800 rounded-xl p-8 max-h-[90vh] overflow-y-auto shadow-2xl">
            <h2 class="text-3xl font-serif text-center mb-2">Secure Checkout</h2>
            <p class="text-center text-blue-300 mb-8 text-sm">Simulation Mode - No Real Payments</p>

            <form onsubmit="processPayment(event)" class="space-y-6">
                
                <!-- Shipping Info -->
                <div class="space-y-4">
                    <h3 class="text-lg font-bold text-blue-200 border-b border-blue-800 pb-2">Shipping Details</h3>
                    <div class="grid grid-cols-1 md:grid-cols-2 gap-4">
                        <input type="text" placeholder="Full Name" required class="bg-[#050914] border border-blue-900 rounded p-3 w-full focus:border-blue-500 outline-none">
                        <input type="email" placeholder="Email Address" required class="bg-[#050914] border border-blue-900 rounded p-3 w-full focus:border-blue-500 outline-none">
                    </div>
                    <input type="text" placeholder="Street Address" required class="bg-[#050914] border border-blue-900 rounded p-3 w-full focus:border-blue-500 outline-none">
                    <div class="grid grid-cols-2 md:grid-cols-3 gap-4">
                        <input type="text" placeholder="City" required class="bg-[#050914] border border-blue-900 rounded p-3 w-full focus:border-blue-500 outline-none">
                        <input type="text" placeholder="State" required class="bg-[#050914] border border-blue-900 rounded p-3 w-full focus:border-blue-500 outline-none">
                        <input type="text" placeholder="Zip" required class="bg-[#050914] border border-blue-900 rounded p-3 w-full focus:border-blue-500 outline-none">
                    </div>
                </div>

                <!-- Payment Info -->
                <div class="space-y-4">
                    <h3 class="text-lg font-bold text-blue-200 border-b border-blue-800 pb-2">Payment Method</h3>
                    <div class="bg-blue-900 bg-opacity-20 p-4 rounded border border-blue-800 mb-2">
                        <p class="text-xs text-blue-300 mb-1">SIMULATION CARD ONLY</p>
                        <p class="text-xs text-red-400">Do not enter real financial data.</p>
                    </div>
                    
                    <div class="grid grid-cols-1 gap-4">
                        <div>
                            <label class="block text-xs text-blue-300 mb-1">Card Number (Max 6 Digits)</label>
                            <input type="text" pattern="\d{1,6}" maxlength="6" placeholder="123456" required class="bg-[#050914] border border-blue-900 rounded p-3 w-full focus:border-blue-500 outline-none text-lg tracking-widest">
                        </div>
                        <div class="grid grid-cols-2 gap-4">
                            <input type="text" placeholder="MM/YY" required class="bg-[#050914] border border-blue-900 rounded p-3 w-full focus:border-blue-500 outline-none">
                            <input type="text" maxlength="3" placeholder="CVC" required class="bg-[#050914] border border-blue-900 rounded p-3 w-full focus:border-blue-500 outline-none">
                        </div>
                    </div>
                </div>

                <div class="pt-4">
                    <button type="submit" class="w-full bg-gradient-to-r from-blue-600 to-blue-800 hover:from-blue-500 hover:to-blue-700 text-white py-4 rounded font-bold shadow-lg transform active:scale-95 transition">
                        COMPLETE ORDER
                    </button>
                    <button type="button" onclick="closeCheckout()" class="w-full mt-2 text-blue-400 hover:text-white py-2 text-sm">Cancel</button>
                </div>
            </form>
        </div>
    </div>

    <!-- Success Overlay -->
    <div id="success-overlay" class="fixed inset-0 z-[80] bg-[#02041a] flex items-center justify-center opacity-0 pointer-events-none transition-opacity duration-1000">
        <div class="text-center p-6">
            <div class="mb-6 inline-block p-4 rounded-full bg-blue-900 bg-opacity-30 border border-blue-500 shadow-[0_0_50px_rgba(59,130,246,0.5)]">
                <i data-lucide="check" class="w-16 h-16 text-blue-400"></i>
            </div>
            <h2 class="text-4xl md:text-6xl font-serif mb-4 text-white">ur order has been sent</h2>
            <p class="text-blue-300 fancy-font text-xl">Thank you for supporting Rey Ivy Rose.</p>
            <button onclick="resetStore()" class="mt-10 px-8 py-3 border border-blue-500 text-blue-400 hover:bg-blue-900 hover:text-white transition rounded">
                Return to Store
            </button>
        </div>
    </div>

    <script>
        // Initialize Icons
        lucide.createIcons();

        // --- Cart Logic ---
        let cart = [];

        function addToCart(title, selectId, img) {
            const select = document.getElementById(selectId);
            const value = select.value; // Format: "Type - $Price"
            const [type, priceStr] = value.split(' - $');
            const price = parseFloat(priceStr);

            cart.push({ title, type, price, img });
            updateCartUI();
            openCart();
        }

        function removeFromCart(index) {
            cart.splice(index, 1);
            updateCartUI();
        }

        function updateCartUI() {
            const cartItemsContainer = document.getElementById('cart-items');
            const cartCount = document.getElementById('cart-count');
            const cartTotal = document.getElementById('cart-total');
            
            // Update count
            cartCount.textContent = cart.length;
            cartCount.style.opacity = cart.length > 0 ? '1' : '0';

            // Update list
            cartItemsContainer.innerHTML = '';
            let total = 0;

            if (cart.length === 0) {
                cartItemsContainer.innerHTML = '<p class="text-center text-gray-500 mt-10 fancy-font">Your cart is empty, like a void...</p>';
            } else {
                cart.forEach((item, index) => {
                    total += item.price;
                    const itemEl = document.createElement('div');
                    itemEl.className = 'flex items-center gap-4 bg-blue-900 bg-opacity-20 p-3 rounded border border-blue-800';
                    itemEl.innerHTML = `
                        <div class="w-16 h-16 flex-shrink-0 overflow-hidden rounded bg-black">
                            <img src="${item.img}" class="w-full h-full object-cover opacity-80" onerror="this.src='https://via.placeholder.com/150/1e2a4a/ffffff?text=Music'">
                        </div>
                        <div class="flex-grow">
                            <h4 class="font-serif text-sm">${item.title}</h4>
                            <p class="text-xs text-blue-300">${item.type}</p>
                            <p class="text-sm font-bold mt-1">$${item.price.toFixed(2)}</p>
                        </div>
                        <button onclick="removeFromCart(${index})" class="text-red-400 hover:text-red-300">
                            <i data-lucide="trash-2" class="w-4 h-4"></i>
                        </button>
                    `;
                    cartItemsContainer.appendChild(itemEl);
                });
                lucide.createIcons();
            }

            cartTotal.textContent = '$' + total.toFixed(2);
        }

        // --- Modal Logic ---
        function openCart() {
            const modal = document.getElementById('cart-modal');
            const panel = document.getElementById('cart-panel');
            modal.classList.add('active');
            panel.classList.remove('translate-x-full');
        }

        function closeCart() {
            const modal = document.getElementById('cart-modal');
            const panel = document.getElementById('cart-panel');
            panel.classList.add('translate-x-full');
            setTimeout(() => {
                modal.classList.remove('active');
            }, 300);
        }

        function goToCheckout() {
            if (cart.length === 0) return;
            closeCart();
            document.getElementById('checkout-modal').classList.add('active');
        }

        function closeCheckout() {
            document.getElementById('checkout-modal').classList.remove('active');
        }

        function processPayment(e) {
            e.preventDefault();
            closeCheckout();
            
            // Show success
            const successOverlay = document.getElementById('success-overlay');
            successOverlay.style.opacity = '1';
            successOverlay.style.pointerEvents = 'all';
            
            // Create confetti/particle explosion effect here if desired
            initParticles(true); 
        }

        function resetStore() {
            cart = [];
            updateCartUI();
            document.getElementById('success-overlay').style.opacity = '0';
            document.getElementById('success-overlay').style.pointerEvents = 'none';
            initParticles(false); // Reset particles to normal
        }

        // --- Particle Background System ---
        const canvas = document.getElementById('particle-canvas');
        const ctx = canvas.getContext('2d');
        let particles = [];
        let animationId;
        let isSuccessMode = false;

        function resizeCanvas() {
            canvas.width = window.innerWidth;
            canvas.height = window.innerHeight;
        }
        window.addEventListener('resize', resizeCanvas);
        resizeCanvas();

        class Particle {
            constructor(x, y, speedMultipier) {
                this.x = x || Math.random() * canvas.width;
                this.y = y || Math.random() * canvas.height;
                this.size = Math.random() * 3 + 1;
                this.speedX = Math.random() * 1 - 0.5;
                this.speedY = Math.random() * 1 - 0.5;
                this.color = this.getColor();
                
                if (isSuccessMode) {
                    this.speedY = Math.random() * -5 - 2; // Fast upward
                    this.speedX = (Math.random() - 0.5) * 4;
                }
            }

            getColor() {
                // Mix of blues and rose colors
                const colors = [
                    'rgba(79, 109, 150, 0.5)', // Accent Blue
                    'rgba(224, 230, 237, 0.3)', // Silver
                    'rgba(30, 42, 74, 0.4)',    // Rose Blue
                    'rgba(100, 10, 40, 0.4)'    // Deep Rose Red (Subtle)
                ];
                return colors[Math.floor(Math.random() * colors.length)];
            }

            update() {
                this.x += this.speedX;
                this.y += this.speedY;

                // Wrap around screen (Normal mode)
                if (!isSuccessMode) {
                    if (this.x > canvas.width) this.x = 0;
                    if (this.x < 0) this.x = canvas.width;
                    if (this.y > canvas.height) this.y = 0;
                    if (this.y < 0) this.y = canvas.height;
                }
            }

            draw() {
                ctx.fillStyle = this.color;
                ctx.beginPath();
                ctx.arc(this.x, this.y, this.size, 0, Math.PI * 2);
                ctx.fill();
            }
        }

        function initParticles(success = false) {
            isSuccessMode = success;
            particles = [];
            const count = success ? 300 : 100; // More particles on success
            
            for (let i = 0; i < count; i++) {
                if (success) {
                    // Start from bottom center
                    particles.push(new Particle(canvas.width / 2, canvas.height + 20));
                } else {
                    particles.push(new Particle());
                }
            }
        }

        function animate() {
            ctx.clearRect(0, 0, canvas.width, canvas.height);
            particles.forEach(p => {
                p.update();
                p.draw();
            });
            animationId = requestAnimationFrame(animate);
        }

        initParticles();
        animate();

    </script>
</body>
</html>
