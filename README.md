<!DOCTYPE html>
<html lang="es" class="h-full">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>LA CRUDERIA - Menú Digital</title>
    <!-- Tailwind CSS CDN -->
    <script src="https://cdn.tailwindcss.com"></script>
    <script>
        tailwind.config = {
            theme: {
                extend: {
                    colors: {
                        brand: {
                            dark: '#0a0a0c',
                            card: '#141419',
                            border: '#2a2721',
                            gold: '#d4af37',
                            goldHover: '#f4c430',
                            goldDark: '#aa7c11',
                            bronze: '#e0a96d'
                        }
                    },
                    fontFamily: {
                        sans: ['Inter', 'sans-serif'],
                        serif: ['Playfair Display', 'Georgia', 'serif']
                    }
                }
            }
        }
    </script>
    <link href="https://fonts.googleapis.com/css2?family=Inter:wght@300;400;500;600;700&family=Playfair+Display:ital,wght@0,600;0,700;0,800;1,400&display=swap" rel="stylesheet">
    <!-- FontAwesome Icons -->
    <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.4.0/css/all.min.css">
    <style>
        body {
            background-color: #08080a;
            color: #f3f4f6;
            background-image: 
                radial-gradient(circle at 50% 0%, rgba(212, 175, 55, 0.07) 0%, transparent 50%),
                radial-gradient(circle at 100% 100%, rgba(170, 124, 17, 0.05) 0%, transparent 40%);
            background-attachment: fixed;
        }

        .glass-card {
            background: rgba(20, 20, 25, 0.85);
            backdrop-filter: blur(14px);
            -webkit-backdrop-filter: blur(14px);
            border: 1px solid rgba(212, 175, 55, 0.2);
        }

        .glass-header {
            background: rgba(10, 10, 12, 0.94);
            backdrop-filter: blur(16px);
            -webkit-backdrop-filter: blur(16px);
            border-bottom: 1px solid rgba(212, 175, 55, 0.2);
        }

        .gold-gradient-text {
            background: linear-gradient(135deg, #fff2a3 0%, #d4af37 50%, #aa7c11 100%);
            -webkit-background-clip: text;
            -webkit-text-fill-color: transparent;
        }

        /* Custom Scrollbar */
        ::-webkit-scrollbar {
            width: 6px;
            height: 6px;
        }
        ::-webkit-scrollbar-track {
            background: #08080a;
        }
        ::-webkit-scrollbar-thumb {
            background: #2a2721;
            border-radius: 4px;
        }
        ::-webkit-scrollbar-thumb:hover {
            background: #d4af37;
        }

        .badge-pulse {
            box-shadow: 0 0 0 0 rgba(212, 175, 55, 0.7);
            animation: pulse 1.5s infinite;
        }

        @keyframes pulse {
            0% { transform: scale(0.95); box-shadow: 0 0 0 0 rgba(212, 175, 55, 0.7); }
            70% { transform: scale(1); box-shadow: 0 0 0 8px rgba(212, 175, 55, 0); }
            100% { transform: scale(0.95); box-shadow: 0 0 0 0 rgba(212, 175, 55, 0); }
        }
    </style>
</head>
<body class="h-full flex flex-col font-sans antialiased pb-24 lg:pb-0">

    <!-- TOP ANNOUNCEMENT BAR (Share / Socials) -->
    <div class="bg-black/95 border-b border-brand-gold/30 px-4 py-2 text-xs relative z-50">
        <div class="max-w-7xl mx-auto flex flex-wrap items-center justify-between gap-2">
            <div class="flex items-center gap-3">
                <a href="https://instagram.com/lacruderiamtl" target="_blank" rel="noopener noreferrer" class="text-brand-gold hover:text-white flex items-center gap-1.5 font-semibold transition">
                    <i class="fa-brands fa-instagram text-sm"></i> @lacruderiamtl
                </a>
                <span class="text-gray-700">|</span>
                <a href="tel:5148135315" class="text-gray-300 hover:text-brand-gold flex items-center gap-1 transition">
                    <i class="fa-solid fa-phone text-[10px] text-brand-gold"></i> 514-813-5315
                </a>
            </div>
            
            <button onclick="copyMenuLink()" class="bg-brand-gold/10 hover:bg-brand-gold/20 text-brand-gold border border-brand-gold/40 px-3 py-1 rounded-full flex items-center gap-1.5 transition text-[11px]">
                <i class="fa-solid fa-share-nodes"></i>
                <span id="copyLinkText">Copiar Link para Bio</span>
            </button>
        </div>
    </div>

    <!-- MAIN APP WRAPPER (Desktop Sidebar + Content + Desktop Cart Sidebar) -->
    <div class="flex-grow max-w-7xl w-full mx-auto px-4 py-4 lg:py-8 flex flex-col lg:flex-row gap-8">

        <!-- DESKTOP LEFT SIDEBAR (Sticky Info & Hours) -->
        <aside class="w-full lg:w-80 flex-shrink-0 space-y-6">
            <div class="glass-card rounded-2xl p-6 border border-brand-gold/30 text-center relative overflow-hidden shadow-2xl lg:sticky lg:top-8">
                <!-- Decorative Crown Background -->
                <div class="absolute -right-6 -top-6 opacity-5 pointer-events-none">
                    <i class="fa-solid fa-crown text-9xl text-brand-gold"></i>
                </div>

                <!-- Logo / Title Header -->
                <div class="mb-5">
                    <span class="inline-block px-3 py-0.5 text-[10px] font-bold uppercase tracking-widest text-brand-gold bg-brand-gold/10 border border-brand-gold/30 rounded-full mb-2">
                        Cocina Mexicana
                    </span>
                    <h1 class="font-serif text-3xl font-extrabold tracking-widest gold-gradient-text">
                        LA CRUDERIA
                    </h1>
                    <p class="text-[11px] font-medium tracking-wider text-gray-400 uppercase mt-1">
                        MARISCOS & CEVICHES • CARNITAS EL MATATAN
                    </p>
                </div>

                <div class="h-px w-full bg-gradient-to-r from-transparent via-brand-gold/40 to-transparent my-4"></div>

                <!-- Language Switcher -->
                <div class="mb-5 flex items-center justify-between bg-black/60 p-2 rounded-xl border border-brand-gold/20">
                    <span class="text-xs text-gray-400 pl-2 font-medium">Idioma / Lang:</span>
                    <select id="langSelector" onchange="changeLanguage(this.value)" 
                        class="bg-brand-card text-brand-gold font-semibold text-xs border border-brand-gold/40 rounded-lg px-2.5 py-1 focus:outline-none focus:border-brand-gold cursor-pointer">
                        <option value="es">🇪🇸 Español</option>
                        <option value="en">🇺🇸 English</option>
                        <option value="fr">🇫🇷 Français</option>
                    </select>
                </div>

                <!-- Locations -->
                <div class="space-y-3 text-left text-xs mb-5">
                    <div class="flex items-start gap-2.5 bg-black/40 p-3 rounded-xl border border-brand-gold/10">
                        <i class="fa-solid fa-location-dot text-brand-gold mt-0.5 text-sm"></i>
                        <div>
                            <p class="font-bold text-white">1121 Rue Bélanger</p>
                            <p class="text-[11px] text-gray-400">Montréal, QC H2S 1H6</p>
                        </div>
                    </div>
                    <div class="flex items-start gap-2.5 bg-black/40 p-3 rounded-xl border border-brand-gold/10">
                        <i class="fa-solid fa-store text-brand-gold mt-0.5 text-sm"></i>
                        <div>
                            <p class="font-bold text-white">6818 Rue St-Hubert</p>
                            <p class="text-[11px] text-gray-400">Plaza Latina • Montréal, QC</p>
                        </div>
                    </div>
                </div>

                <!-- Operating Hours Table -->
                <div class="bg-gradient-to-b from-brand-gold/10 to-transparent p-4 rounded-xl border border-brand-gold/30 text-left text-xs space-y-2 mb-5">
                    <div class="flex items-center gap-2 font-bold text-brand-gold uppercase tracking-wider text-[11px] mb-2">
                        <i class="fa-solid fa-clock"></i>
                        <span id="hoursHeading">Horario de Atención</span>
                    </div>
                    <div class="space-y-1.5 text-gray-200">
                        <div class="flex justify-between border-b border-white/10 pb-1">
                            <span class="text-gray-400">Lun - Mié:</span>
                            <span class="font-semibold text-white">9:00 AM – 9:00 PM</span>
                        </div>
                        <div class="flex justify-between border-b border-white/10 pb-1 text-red-400">
                            <span class="font-medium">Jueves:</span>
                            <span class="font-bold">CERRADO</span>
                        </div>
                        <div class="flex justify-between text-brand-gold">
                            <span class="font-medium">Vie - Dom:</span>
                            <span class="font-bold">8:00 AM – 4:00 PM</span>
                        </div>
                    </div>
                </div>

                <!-- Direct Contact Buttons -->
                <div class="grid grid-cols-2 gap-2 text-xs">
                    <a href="tel:5148135315" class="bg-black hover:bg-brand-gold/20 text-gray-200 border border-brand-gold/40 p-2.5 rounded-xl font-medium transition flex items-center justify-center gap-1.5">
                        <i class="fa-solid fa-phone text-brand-gold"></i> Llamar
                    </a>
                    <a href="https://wa.me/5146416351" target="_blank" class="bg-emerald-700/80 hover:bg-emerald-600 text-white p-2.5 rounded-xl font-semibold transition flex items-center justify-center gap-1.5">
                        <i class="fa-brands fa-whatsapp text-sm"></i> WhatsApp
                    </a>
                </div>
            </div>
        </aside>

        <!-- CENTER AREA: MENU CONTENT -->
        <main class="flex-grow space-y-6">
            
            <!-- STICKY CATEGORY & SEARCH BAR -->
            <div class="sticky top-2 z-30 glass-header rounded-2xl p-3 border border-brand-gold/30 shadow-xl space-y-3">
                <div class="flex items-center gap-3">
                    <!-- Search Field -->
                    <div class="relative flex-grow">
                        <i class="fa-solid fa-magnifying-glass absolute left-3 top-1/2 -translate-y-1/2 text-brand-gold/60 text-xs"></i>
                        <input type="text" id="searchInput" oninput="handleSearch()" placeholder="Buscar platillos / Search menu..." 
                            class="w-full bg-black/80 border border-brand-gold/30 rounded-xl pl-9 pr-8 py-2 text-xs text-gray-100 placeholder-gray-500 focus:outline-none focus:border-brand-gold transition">
                        <button id="clearSearch" onclick="clearSearchInput()" class="hidden absolute right-3 top-1/2 -translate-y-1/2 text-gray-400 hover:text-white text-xs">
                            <i class="fa-solid fa-xmark"></i>
                        </button>
                    </div>
                </div>

                <!-- Horizontal Filter Chips -->
                <div class="overflow-x-auto no-scrollbar pt-1">
                    <div class="flex items-center gap-2 min-w-max" id="categoryNav">
                        <!-- Dynamic Categories -->
                    </div>
                </div>
            </div>

            <!-- MENU ITEMS CONTAINER -->
            <div id="menuContainer" class="space-y-10">
                <!-- Dynamic Menu Sections rendered here -->
            </div>

            <!-- No Results Found -->
            <div id="noResults" class="hidden text-center py-16">
                <i class="fa-solid fa-magnifying-glass text-4xl text-brand-gold/40 mb-3"></i>
                <h3 class="text-lg font-semibold text-white mb-1" id="noResultsTitle">No se encontraron resultados</h3>
                <p class="text-xs text-gray-400" id="noResultsDesc">Intenta buscar con otra palabra clave o selecciona otra categoría.</p>
            </div>
        </main>

        <!-- DESKTOP RIGHT SIDEBAR (PERSISTENT ORDER WIDGET) -->
        <aside class="hidden lg:block w-80 flex-shrink-0">
            <div class="glass-card rounded-2xl p-5 border border-brand-gold/30 sticky top-8 shadow-2xl space-y-4">
                <div class="flex items-center justify-between border-b border-brand-gold/20 pb-3">
                    <div class="flex items-center gap-2">
                        <i class="fa-solid fa-receipt text-brand-gold"></i>
                        <h3 class="font-serif font-bold text-white text-base" id="desktopOrderTitle">Tu Pedido</h3>
                    </div>
                    <span id="desktopBadge" class="bg-brand-gold text-black text-xs font-bold px-2 py-0.5 rounded-full">
                        0
                    </span>
                </div>

                <!-- Cart Items List Desktop -->
                <div class="max-h-96 overflow-y-auto space-y-2.5 pr-1" id="desktopCartList">
                    <!-- Items populated dynamically -->
                </div>

                <div class="border-t border-brand-gold/20 pt-3 space-y-3">
                    <div class="flex justify-between items-center text-sm">
                        <span class="text-gray-400" id="desktopSubtotalLabel">Subtotal Estimado:</span>
                        <span class="text-xl font-bold font-serif text-brand-gold" id="desktopTotal">$0.00</span>
                    </div>

                    <button onclick="sendOrderToWhatsApp()" class="w-full bg-emerald-600 hover:bg-emerald-500 text-white py-3 rounded-xl font-bold text-xs shadow-lg transition flex items-center justify-center gap-2">
                        <i class="fa-brands fa-whatsapp text-base"></i>
                        <span id="desktopWhatsappBtn">Pedir por WhatsApp</span>
                    </button>
                    
                    <button onclick="clearCart()" class="w-full text-xs text-gray-400 hover:text-red-400 py-1 transition text-center">
                        <i class="fa-solid fa-trash-can mr-1"></i> <span id="desktopClearBtn">Vaciar Carrito</span>
                    </button>
                </div>
            </div>
        </aside>

    </div>

    <!-- FOOTER COMPLIMENTARY NOTE -->
    <footer class="mt-auto border-t border-brand-gold/20 bg-black/95 py-6 px-4">
        <div class="max-w-4xl mx-auto text-center space-y-3">
            <div class="inline-flex items-center justify-center p-2 px-4 rounded-full bg-brand-card border border-brand-gold/30 text-xs text-gray-200 font-medium">
                <i class="fa-solid fa-gift text-brand-gold mr-2 text-sm"></i>
                <span id="footerNote">Nuestras órdenes incluyen guarnición del día y consomé de cortesía.</span>
            </div>

            <p class="text-xs text-gray-400">
                1121 Rue Bélanger & 6818 Rue St-Hubert • Montréal, Québec, Canada
            </p>

            <p class="text-[11px] text-gray-600">
                &copy; <span id="year"></span> LA CRUDERIA. Todos los derechos reservados.
            </p>
        </div>
    </footer>

    <!-- MOBILE FLOATING CART BAR (Shown only on small screens) -->
    <div id="cartBar" class="lg:hidden fixed bottom-4 left-1/2 -translate-x-1/2 z-50 w-[92%] max-w-lg glass-card rounded-2xl p-3 shadow-2xl border border-brand-gold/50 hidden transition-all duration-300">
        <div class="flex items-center justify-between gap-3">
            <div class="flex items-center gap-3">
                <div class="relative bg-brand-gold/20 text-brand-gold p-2.5 rounded-xl border border-brand-gold/40">
                    <i class="fa-solid fa-bag-shopping text-lg"></i>
                    <span id="cartBadge" class="absolute -top-2 -right-2 bg-brand-gold text-black text-[10px] font-extrabold w-5 h-5 rounded-full flex items-center justify-center badge-pulse">
                        0
                    </span>
                </div>
                <div>
                    <span class="text-[10px] text-gray-400 uppercase tracking-wider block" id="cartLabel">Tu Orden</span>
                    <span class="text-base font-bold text-white font-serif" id="cartTotal">$0.00</span>
                </div>
            </div>

            <button onclick="toggleCartModal(true)" class="bg-gradient-to-r from-brand-gold to-brand-goldDark hover:opacity-90 text-black font-extrabold text-xs px-4 py-2.5 rounded-xl shadow-lg transition flex items-center gap-2">
                <span id="viewOrderBtn">Ver Pedido</span>
                <i class="fa-solid fa-arrow-right text-xs"></i>
            </button>
        </div>
    </div>

    <!-- MOBILE CART MODAL -->
    <div id="cartModal" class="lg:hidden fixed inset-0 z-50 bg-black/85 backdrop-blur-md flex items-end justify-center p-0 opacity-0 pointer-events-none transition-opacity duration-300">
        <div class="bg-brand-card border border-brand-gold/40 w-full rounded-t-3xl max-h-[85vh] flex flex-col shadow-2xl transform translate-y-full transition-transform duration-300" id="cartModalContent">
            
            <div class="p-4 border-b border-brand-gold/20 flex items-center justify-between">
                <div class="flex items-center gap-2">
                    <i class="fa-solid fa-receipt text-brand-gold text-lg"></i>
                    <h3 class="font-serif text-lg font-bold text-white" id="modalTitle">Detalle de tu Pedido</h3>
                </div>
                <button onclick="toggleCartModal(false)" class="text-gray-400 hover:text-white w-8 h-8 rounded-full bg-black flex items-center justify-center border border-brand-gold/30">
                    <i class="fa-solid fa-xmark"></i>
                </button>
            </div>

            <div class="p-4 overflow-y-auto flex-grow space-y-3" id="cartItemList">
                <!-- Mobile Cart items -->
            </div>

            <div class="p-4 border-t border-brand-gold/20 bg-black/60 space-y-3">
                <div class="flex justify-between items-center text-sm">
                    <span class="text-gray-400" id="subtotalLabel">Subtotal Estimado:</span>
                    <span class="text-xl font-bold font-serif text-brand-gold" id="modalTotal">$0.00</span>
                </div>

                <div class="flex gap-2">
                    <button onclick="clearCart()" class="w-1/3 py-2.5 px-3 rounded-xl border border-red-500/30 text-red-400 hover:bg-red-500/10 text-xs font-semibold transition flex items-center justify-center gap-1.5">
                        <i class="fa-solid fa-trash-can"></i>
                        <span id="clearCartBtn">Vaciar</span>
                    </button>
                    <button onclick="sendOrderToWhatsApp()" class="w-2/3 bg-emerald-600 hover:bg-emerald-500 text-white py-2.5 px-3 rounded-xl font-bold text-xs shadow-lg transition flex items-center justify-center gap-2">
                        <i class="fa-brands fa-whatsapp text-lg"></i>
                        <span id="whatsappBtnText">Pedir por WhatsApp</span>
                    </button>
                </div>
            </div>
        </div>
    </div>

    <!-- TOAST NOTIFICATION -->
    <div id="toast" class="fixed top-16 right-4 z-50 bg-brand-card border border-brand-gold text-white px-4 py-3 rounded-xl shadow-2xl flex items-center gap-3 transform translate-x-full transition-transform duration-300">
        <i class="fa-solid fa-circle-check text-brand-gold text-lg"></i>
        <span text-xs id="toastMsg">Producto agregado a tu orden</span>
    </div>

    <!-- JAVASCRIPT LOGIC -->
    <script>
        document.getElementById('year').innerText = new Date().getFullYear();

        function copyMenuLink() {
            const tempInput = document.createElement('input');
            tempInput.value = window.location.href;
            document.body.appendChild(tempInput);
            tempInput.select();
            document.execCommand('copy');
            document.body.removeChild(tempInput);

            const copyBtnText = document.getElementById('copyLinkText');
            const originalText = copyBtnText.innerText;
            copyBtnText.innerText = '¡Copiado!';
            setTimeout(() => {
                copyBtnText.innerText = originalText;
            }, 2000);
        }

        const menuData = [
            {
                id: 'cat_entradas',
                key: 'entradas',
                names: { es: 'ENTRADAS', en: 'APPETIZERS', fr: 'ENTRÉES' },
                icon: 'fa-shrimp',
                items: [
                    {
                        id: 'e1',
                        price: 15,
                        image: 'https://images.unsplash.com/photo-1599974579688-8dbdd335c77f?w=500&auto=format&fit=crop&q=80',
                        names: { es: 'Tostada Camarón', en: 'Shrimp Tostada', fr: 'Tostada aux crevettes' },
                        desc: { es: 'Tostada crujiente con camarones frescos, verduras y aguacate.', en: 'Crispy tostada with fresh shrimp, vegetables and avocado.', fr: 'Tostada croustillante aux crevettes fraîches et avocat.' }
                    },
                    {
                        id: 'e2',
                        price: 20,
                        image: 'https://images.unsplash.com/photo-1535399831218-d5bd36d1a6b3?w=500&auto=format&fit=crop&q=80',
                        names: { es: 'Ceviche', en: 'Ceviche', fr: 'Ceviche' },
                        desc: { es: 'Pescado y mariscos marinados en cítricos con cilantro y cebolla.', en: 'Fresh fish and seafood marinated in citrus with cilantro and onion.', fr: 'Poisson frais et fruits de mer marinés au citron vert.' }
                    },
                    {
                        id: 'e3',
                        price: 20,
                        image: 'https://images.unsplash.com/photo-1565557623262-b51c2513a641?w=500&auto=format&fit=crop&q=80',
                        names: { es: 'Cóctel', en: 'Shrimp Cocktail', fr: 'Cocktail de crevettes' },
                        desc: { es: 'Cóctel tradicional de camarón en salsa casera con aguacate.', en: 'Traditional shrimp cocktail in house tomato sauce with avocado.', fr: 'Cocktail traditionnel de crevettes avec sauce maison et avocat.' }
                    },
                    {
                        id: 'e4',
                        price: 20,
                        image: 'https://images.unsplash.com/photo-1579631542720-3a87824fff86?w=500&auto=format&fit=crop&q=80',
                        names: { es: 'Vuelve a la Vida', en: 'Seafood Cocktail', fr: 'Cocktail de fruits de mer' },
                        desc: { es: 'Combinación especial de mariscos surtidos marinados.', en: 'Special mixed seafood cocktail in flavorful citrus juices.', fr: 'Mélange spécial de fruits de mer marinés.' }
                    }
                ]
            },
            {
                id: 'cat_burritos',
                key: 'burritos',
                names: { es: 'BURRITOS', en: 'BURRITOS', fr: 'BURRITOS' },
                icon: 'fa-scroll',
                description: {
                    es: 'Con proteína a elegir de nuestra selección de tacos',
                    en: 'Choice of protein from our taco selection',
                    fr: 'Protéine au choix parmi notre sélection de tacos'
                },
                items: [
                    {
                        id: 'b1',
                        price: 20,
                        image: 'https://images.unsplash.com/photo-1626700051175-6818013e1d4f?w=500&auto=format&fit=crop&q=80',
                        names: { es: 'Burrito Especial', en: 'Special Burrito', fr: 'Burrito Spécial' },
                        desc: { es: 'Tortilla grande de harina rellena de frijoles, queso y tu proteína favorita.', en: 'Large flour tortilla filled with beans, cheese, and your protein of choice.', fr: 'Grande tortilla avec haricots, fromage fondu et protéine au choix.' }
                    }
                ]
            },
            {
                id: 'cat_tacos',
                key: 'tacos',
                names: { es: 'TACOS', en: 'TACOS', fr: 'TACOS' },
                icon: 'fa-cloud-meatball',
                items: [
                    { id: 't1', price: 20, image: 'https://images.unsplash.com/photo-1551504734-5ee1c4a1479b?w=500&auto=format&fit=crop&q=80', names: { es: 'Sirloin', en: 'Sirloin Tacos', fr: 'Tacos de surlonge' }, desc: { es: 'Corte de sirloin a la parrilla sobre tortilla de maíz.', en: 'Grilled sirloin steak served on warm corn tortillas.', fr: 'Surlonge grillée sur tortilla de maïs.' } },
                    { id: 't2', price: 20, image: 'https://images.unsplash.com/photo-1565299585323-38d6b0865b47?w=500&auto=format&fit=crop&q=80', names: { es: 'Pastor', en: 'Marinated Pork / Al Pastor', fr: 'Porc mariné / al Pastor' }, desc: { es: 'Cerdo marinado con especias y piña asada.', en: 'Marinated pork with spices and roasted pineapple.', fr: 'Porc mariné aux épices et ananas rôti.' } },
                    { id: 't3', price: 20, image: 'https://images.unsplash.com/photo-1615870216519-2f9fa575fa5c?w=500&auto=format&fit=crop&q=80', names: { es: 'Carnitas', en: 'Braised Pork Tacos', fr: 'Tacos de porc braisé' }, desc: { es: 'Carnitas jugosas confitadas estilo artesanal.', en: 'Slow-cooked tender pork carnitas.', fr: 'Porc confit très tendre et savoureux.' } },
                    { id: 't4', price: 20, image: 'https://images.unsplash.com/photo-1599974579688-8dbdd335c77f?w=500&auto=format&fit=crop&q=80', names: { es: 'Chorizo', en: 'Chorizo Tacos', fr: 'Tacos au chorizo' }, desc: { es: 'Chorizo sazonado a la plancha.', en: 'Mexican style chorizo cooked to perfection.', fr: 'Chorizo mexicain doré à la plaque.' } },
                    { id: 't5', price: 20, image: 'https://images.unsplash.com/photo-1613514785940-daed07799d9b?w=500&auto=format&fit=crop&q=80', names: { es: 'Pollo en su Jugo', en: 'Chicken in its juices', fr: 'Poulet dans son jus' }, desc: { es: 'Pechuga sazonada jugosa y llena de sabor.', en: 'Seasoned chicken breast cooked in rich broth.', fr: 'Poitrine de poulet savoureuse dans son jus.' } },
                    { id: 't6', price: 20, image: 'https://images.unsplash.com/photo-1565299585323-38d6b0865b47?w=500&auto=format&fit=crop&q=80', names: { es: 'Camarón', en: 'Shrimp Tacos', fr: 'Tacos aux crevettes' }, desc: { es: 'Camarones salteados con mantequilla y ajo.', en: 'Butter garlic sautéed delicious shrimp.', fr: 'Crevettes sautées au beurre d\'ail.' } },
                    { id: 't7', price: 20, image: 'https://images.unsplash.com/photo-1551504734-5ee1c4a1479b?w=500&auto=format&fit=crop&q=80', names: { es: 'Suadero', en: 'Mexican-Style Beef Tacos', fr: 'Tacos de bœuf à la mexicaine' }, desc: { es: 'Carne suave de res cocinada a fuego lento.', en: 'Tender beef cut prepared traditionally.', fr: 'Morceau de bœuf tendre cuit à la mexicaine.' } },
                    { id: 't8', price: 25, image: 'https://images.unsplash.com/photo-1626700051175-6818013e1d4f?w=500&auto=format&fit=crop&q=80', names: { es: 'Quesabirrias', en: 'Birria Quesadillas', fr: 'Quesadillas à la birria' }, desc: { es: 'Tortilla dorada con queso fundido y birria de res.', en: 'Crispy tortillas filled with melted cheese and birria beef.', fr: 'Tortillas croustillantes au fromage fondu et bœuf birria.' } }
                ]
            },
            {
                id: 'cat_caldos',
                key: 'caldos',
                names: { es: 'CALDOS', en: 'SOUPS', fr: 'SOUPES' },
                icon: 'fa-bowl-food',
                items: [
                    { id: 'c1', price: 20, image: 'https://images.unsplash.com/photo-1547592180-85f173990554?w=500&auto=format&fit=crop&q=80', names: { es: 'Caldo Pancita de Res', en: 'Beef Tripe Soup', fr: 'Soupe de tripes de bœuf' }, desc: { es: 'Pancita de res bien sazonada en caldo rojo.', en: 'Traditional Mexican beef tripe soup.', fr: 'Soupe traditionnelle de tripes de bœuf.' } },
                    { id: 'c2', price: 20, image: 'https://images.unsplash.com/photo-1559847844-5315695dadae?w=500&auto=format&fit=crop&q=80', names: { es: 'Caldo Camarón', en: 'Shrimp Soup', fr: 'Soupe aux crevettes' }, desc: { es: 'Caldo sustancioso de camarón con verduras.', en: 'Flavorful shrimp broth cooked with fresh veggies.', fr: 'Bouillon savoureux de crevettes et légumes.' } }
                ]
            },
            {
                id: 'cat_postres',
                key: 'postres',
                names: { es: 'POSTRES', en: 'DESSERTS', fr: 'DESSERTS' },
                icon: 'fa-ice-cream',
                items: [
                    { id: 'p1', price: 15, image: 'https://images.unsplash.com/photo-1517427294546-5aa121f68e8a?w=500&auto=format&fit=crop&q=80', names: { es: 'Arroz con Leche', en: 'Rice Pudding', fr: 'Riz au lait' }, desc: { es: 'Postre cremoso de arroz con canela.', en: 'Creamy rice pudding topped with cinnamon.', fr: 'Riz au lait crémeux parfumé à la cannelle.' } },
                    { id: 'p2', price: 15, image: 'https://images.unsplash.com/photo-1587314168485-3236d6710814?w=500&auto=format&fit=crop&q=80', names: { es: 'Pastel 3 Leches', en: 'Tres Leches Cake', fr: 'Gâteau aux trois laits' }, desc: { es: 'Pastel húmedo bañado en mezcla de 3 leches.', en: 'Sponge cake soaked in rich three-milk syrup.', fr: 'Gâteau moelleux imbibé aux 3 laits.' } },
                    { id: 'p3', price: 15, image: 'https://images.unsplash.com/photo-1528975604071-b4dc52a2d18c?w=500&auto=format&fit=crop&q=80', names: { es: 'Flan Napolitano', en: 'Mexican Flan', fr: 'Flan napolitain' }, desc: { es: 'Flan suave cremoso con salsa de caramelo.', en: 'Rich cream cheese flan with caramel.', fr: 'Flan crémeux nappé de caramel.' } },
                    { id: 'p4', price: 10, image: 'https://images.unsplash.com/photo-1551024709-8f23befc6f87?w=500&auto=format&fit=crop&q=80', names: { es: 'Gelatina Mosaico', en: 'Mosaic Gelatin', fr: 'Gelée mosaïque' }, desc: { es: 'Gelatina de sabores combinada en base láctea.', en: 'Multi-flavored gelatin cubes in sweet cream.', fr: 'Cubes de gelée colorés sur base crémeuse.' } }
                ]
            }
        ];

        const uiText = {
            es: {
                all: 'Todos',
                footerNote: 'Nuestras órdenes incluyen guarnición del día y consomé de cortesía.',
                addBtn: 'Agregar',
                cartLabel: 'Tu Orden',
                viewOrderBtn: 'Ver Pedido',
                modalTitle: 'Detalle de tu Pedido',
                subtotalLabel: 'Subtotal Estimado:',
                clearCartBtn: 'Vaciar',
                desktopOrderTitle: 'Tu Pedido',
                desktopSubtotalLabel: 'Subtotal Estimado:',
                desktopClearBtn: 'Vaciar Carrito',
                desktopWhatsappBtn: 'Pedir por WhatsApp',
                emptyCartMsg: 'Tu pedido está vacío. ¡Agrega algunos platillos!',
                noResultsTitle: 'No se encontraron resultados',
                noResultsDesc: 'Intenta buscar con otra palabra clave o selecciona otra categoría.',
                toastAdded: 'platillo(s) agregado(s) a tu orden.',
                whatsappBtn: 'Pedir por WhatsApp'
            },
            en: {
                all: 'All',
                footerNote: 'Our orders include the side dish of the day and complimentary consommé.',
                addBtn: 'Add',
                cartLabel: 'Your Order',
                viewOrderBtn: 'View Order',
                modalTitle: 'Your Order Details',
                subtotalLabel: 'Estimated Subtotal:',
                clearCartBtn: 'Clear',
                desktopOrderTitle: 'Your Order',
                desktopSubtotalLabel: 'Estimated Subtotal:',
                desktopClearBtn: 'Clear Order',
                desktopWhatsappBtn: 'Order via WhatsApp',
                emptyCartMsg: 'Your order is empty. Add delicious items!',
                noResultsTitle: 'No items found',
                noResultsDesc: 'Try searching for another keyword or change category.',
                toastAdded: 'item(s) added to your order.',
                whatsappBtn: 'Order via WhatsApp'
            },
            fr: {
                all: 'Tous',
                footerNote: 'Nos plats comprennent l\'accompagnement du jour et un consommé offert.',
                addBtn: 'Ajouter',
                cartLabel: 'Votre Commande',
                viewOrderBtn: 'Voir Commande',
                modalTitle: 'Détail de votre Commande',
                subtotalLabel: 'Sous-total Estimé:',
                clearCartBtn: 'Vider',
                desktopOrderTitle: 'Votre Commande',
                desktopSubtotalLabel: 'Sous-total Estimé:',
                desktopClearBtn: 'Vider Panier',
                desktopWhatsappBtn: 'Commander via WhatsApp',
                emptyCartMsg: 'Votre commande est vide. Ajoutez des plats!',
                noResultsTitle: 'Aucun résultat trouvé',
                noResultsDesc: 'Essayez un autre mot-clé ou changez de catégorie.',
                toastAdded: 'article(s) ajouté(s) à votre commande.',
                whatsappBtn: 'Commander via WhatsApp'
            }
        };

        let currentLang = 'es';
        let activeCategory = 'all';
        let searchQuery = '';
        let cart = {};

        document.addEventListener('DOMContentLoaded', () => {
            renderCategoryNav();
            renderMenu();
            updateCartUI();
        });

        function changeLanguage(lang) {
            currentLang = lang;
            document.getElementById('footerNote').innerText = uiText[currentLang].footerNote;
            document.getElementById('cartLabel').innerText = uiText[currentLang].cartLabel;
            document.getElementById('viewOrderBtn').innerText = uiText[currentLang].viewOrderBtn;
            document.getElementById('modalTitle').innerText = uiText[currentLang].modalTitle;
            document.getElementById('subtotalLabel').innerText = uiText[currentLang].subtotalLabel;
            document.getElementById('clearCartBtn').innerText = uiText[currentLang].clearCartBtn;
            document.getElementById('whatsappBtnText').innerText = uiText[currentLang].whatsappBtn;
            document.getElementById('desktopOrderTitle').innerText = uiText[currentLang].desktopOrderTitle;
            document.getElementById('desktopSubtotalLabel').innerText = uiText[currentLang].desktopSubtotalLabel;
            document.getElementById('desktopClearBtn').innerText = uiText[currentLang].desktopClearBtn;
            document.getElementById('desktopWhatsappBtn').innerText = uiText[currentLang].desktopWhatsappBtn;
            document.getElementById('noResultsTitle').innerText = uiText[currentLang].noResultsTitle;
            document.getElementById('noResultsDesc').innerText = uiText[currentLang].noResultsDesc;

            renderCategoryNav();
            renderMenu();
            updateCartUI();
        }

        function renderCategoryNav() {
            const container = document.getElementById('categoryNav');
            let html = `
                <button onclick="filterCategory('all')" 
                    class="px-4 py-1.5 rounded-xl text-xs font-semibold transition border ${activeCategory === 'all' 
                        ? 'bg-gradient-to-r from-brand-gold to-brand-goldDark text-black border-brand-gold shadow-md' 
                        : 'bg-black/60 text-gray-300 border-brand-gold/30 hover:border-brand-gold'}">
                    <i class="fa-solid fa-list border-r border-gray-600/40 pr-1.5 mr-1 text-[10px]"></i> ${uiText[currentLang].all}
                </button>
            `;

            menuData.forEach(cat => {
                const isActive = activeCategory === cat.key;
                html += `
                    <button onclick="filterCategory('${cat.key}')" 
                        class="px-4 py-1.5 rounded-xl text-xs font-semibold transition border flex items-center gap-1.5 ${isActive 
                            ? 'bg-gradient-to-r from-brand-gold to-brand-goldDark text-black border-brand-gold shadow-md' 
                            : 'bg-black/60 text-gray-300 border-brand-gold/30 hover:border-brand-gold'}">
                        <i class="fa-solid ${cat.icon} text-[11px] ${isActive ? 'text-black' : 'text-brand-gold'}"></i>
                        <span>${cat.names[currentLang]}</span>
                    </button>
                `;
            });

            container.innerHTML = html;
        }

        function filterCategory(catKey) {
            activeCategory = catKey;
            renderCategoryNav();
            renderMenu();
        }

        function handleSearch() {
            searchQuery = document.getElementById('searchInput').value.toLowerCase().trim();
            const clearBtn = document.getElementById('clearSearch');
            if (searchQuery.length > 0) {
                clearBtn.classList.remove('hidden');
            } else {
                clearBtn.classList.add('hidden');
            }
            renderMenu();
        }

        function clearSearchInput() {
            document.getElementById('searchInput').value = '';
            searchQuery = '';
            document.getElementById('clearSearch').classList.add('hidden');
            renderMenu();
        }

        function renderMenu() {
            const container = document.getElementById('menuContainer');
            const noResults = document.getElementById('noResults');
            let totalItemsRendered = 0;
            let html = '';

            menuData.forEach(cat => {
                if (activeCategory !== 'all' && activeCategory !== cat.key) return;

                const filteredItems = cat.items.filter(item => {
                    const name = item.names[currentLang].toLowerCase();
                    const desc = item.desc[currentLang].toLowerCase();
                    return name.includes(searchQuery) || desc.includes(searchQuery);
                });

                if (filteredItems.length === 0) return;
                totalItemsRendered += filteredItems.length;

                html += `
                    <section class="space-y-4">
                        <div class="flex items-center gap-3 border-b border-brand-gold/30 pb-2">
                            <div class="w-8 h-8 rounded-lg bg-brand-gold/10 border border-brand-gold/40 flex items-center justify-center text-brand-gold">
                                <i class="fa-solid ${cat.icon} text-sm"></i>
                            </div>
                            <div>
                                <h3 class="font-serif text-xl sm:text-2xl font-bold tracking-wide text-white">
                                    ${cat.names[currentLang]}
                                </h3>
                                ${cat.description ? `
                                    <p class="text-xs text-brand-gold italic mt-0.5">
                                        ${cat.description[currentLang]}
                                    </p>
                                ` : ''}
                            </div>
                        </div>

                        <div class="grid grid-cols-1 md:grid-cols-2 gap-4">
                `;

                filteredItems.forEach(item => {
                    const quantity = cart[item.id] || 0;
                    html += `
                        <div class="glass-card rounded-2xl overflow-hidden hover:border-brand-gold/60 transition duration-300 flex flex-col justify-between group shadow-lg">
                            <div class="flex flex-row p-3.5 sm:p-4 gap-3 sm:gap-4">
                                <div class="relative w-24 h-24 sm:w-28 sm:h-28 rounded-xl overflow-hidden flex-shrink-0 border border-brand-gold/20 bg-black">
                                    <img src="${item.image}" alt="${item.names[currentLang]}" 
                                        onerror="this.onerror=null; this.src='https://placehold.co/200x200/181818/d4af37?text=LA+CRUDERIA';" 
                                        class="w-full h-full object-cover group-hover:scale-105 transition duration-500">
                                </div>

                                <div class="flex-grow flex flex-col justify-between">
                                    <div>
                                        <div class="flex justify-between items-start gap-2 mb-1">
                                            <h4 class="font-semibold text-sm sm:text-base text-white group-hover:text-brand-gold transition">
                                                ${item.names[currentLang]}
                                            </h4>
                                            <span class="font-serif text-base sm:text-lg font-bold text-brand-gold flex-shrink-0">
                                                $${item.price}
                                            </span>
                                        </div>
                                        <p class="text-xs text-gray-400 line-clamp-2 leading-relaxed">
                                            ${item.desc[currentLang]}
                                        </p>
                                    </div>

                                    <div class="mt-3 flex items-center justify-end">
                                        ${quantity > 0 ? `
                                            <div class="flex items-center bg-black border border-brand-gold/50 rounded-xl p-1 gap-3">
                                                <button onclick="updateQuantity('${item.id}', -1)" class="w-7 h-7 rounded-lg bg-brand-gold/20 hover:bg-brand-gold hover:text-black text-brand-gold flex items-center justify-center transition">
                                                    <i class="fa-solid fa-minus text-xs"></i>
                                                </button>
                                                <span class="font-semibold text-xs text-white min-w-[14px] text-center">${quantity}</span>
                                                <button onclick="updateQuantity('${item.id}', 1)" class="w-7 h-7 rounded-lg bg-brand-gold text-black hover:bg-yellow-300 flex items-center justify-center transition font-bold">
                                                    <i class="fa-solid fa-plus text-xs"></i>
                                                </button>
                                            </div>
                                        ` : `
                                            <button onclick="updateQuantity('${item.id}', 1)" class="bg-brand-gold/10 hover:bg-brand-gold/30 border border-brand-gold/40 text-brand-gold hover:text-white px-3 py-1.5 rounded-xl text-xs font-semibold transition flex items-center gap-1.5">
                                                <i class="fa-solid fa-plus text-[10px]"></i>
                                                <span>${uiText[currentLang].addBtn}</span>
                                            </button>
                                        `}
                                    </div>
                                </div>
                            </div>
                        </div>
                    `;
                });

                html += `
                        </div>
                    </section>
                `;
            });

            container.innerHTML = html;

            if (totalItemsRendered === 0) {
                noResults.classList.remove('hidden');
            } else {
                noResults.classList.add('hidden');
            }
        }

        function updateQuantity(itemId, delta) {
            if (!cart[itemId]) cart[itemId] = 0;
            cart[itemId] += delta;
            
            if (cart[itemId] <= 0) {
                delete cart[itemId];
            }

            renderMenu();
            updateCartUI();
            
            if (delta > 0) {
                showToast(`1 ${uiText[currentLang].toastAdded}`);
            }
        }

        function getItemById(id) {
            for (const cat of menuData) {
                const found = cat.items.find(i => i.id === id);
                if (found) return found;
            }
            return null;
        }

        function updateCartUI() {
            let totalCount = 0;
            let totalPrice = 0;

            for (const [id, count] of Object.entries(cart)) {
                const item = getItemById(id);
                if (item) {
                    totalCount += count;
                    totalPrice += item.price * count;
                }
            }

            // Mobile Bar
            const cartBar = document.getElementById('cartBar');
            document.getElementById('cartBadge').innerText = totalCount;
            document.getElementById('cartTotal').innerText = `$${totalPrice.toFixed(2)}`;

            if (totalCount > 0) {
                cartBar.classList.remove('hidden');
            } else {
                cartBar.classList.add('hidden');
            }

            // Desktop Widget
            document.getElementById('desktopBadge').innerText = totalCount;
            document.getElementById('desktopTotal').innerText = `$${totalPrice.toFixed(2)}`;
            document.getElementById('modalTotal').innerText = `$${totalPrice.toFixed(2)}`;

            renderCartModalItems();
            renderDesktopCartItems();
        }

        function renderDesktopCartItems() {
            const listContainer = document.getElementById('desktopCartList');
            let html = '';
            const entries = Object.entries(cart);

            if (entries.length === 0) {
                html = `
                    <div class="text-center py-8 text-gray-500">
                        <i class="fa-solid fa-basket-shopping text-2xl mb-2 text-brand-gold/40"></i>
                        <p class="text-xs">${uiText[currentLang].emptyCartMsg}</p>
                    </div>
                `;
            } else {
                entries.forEach(([id, count]) => {
                    const item = getItemById(id);
                    if (!item) return;

                    const itemTotal = item.price * count;
                    html += `
                        <div class="flex items-center justify-between bg-black/70 p-2.5 rounded-xl border border-brand-gold/20">
                            <div class="flex items-center gap-2.5 flex-grow pr-2">
                                <img src="${item.image}" alt="${item.names[currentLang]}" 
                                    onerror="this.onerror=null; this.src='https://placehold.co/100x100/181818/d4af37?text=Food';" 
                                    class="w-10 h-10 rounded-lg object-cover border border-brand-gold/30 flex-shrink-0">
                                <div>
                                    <h5 class="text-xs font-semibold text-white line-clamp-1">${item.names[currentLang]}</h5>
                                    <p class="text-[11px] text-brand-gold font-serif">$${item.price} c/u</p>
                                </div>
                            </div>
                            <div class="flex items-center gap-2 flex-shrink-0">
                                <div class="flex items-center bg-brand-card border border-brand-gold/30 rounded-lg p-0.5 gap-1.5">
                                    <button onclick="updateQuantity('${item.id}', -1)" class="w-5 h-5 rounded bg-brand-gold/20 text-brand-gold flex items-center justify-center text-[10px]">
                                        <i class="fa-solid fa-minus"></i>
                                    </button>
                                    <span class="text-xs font-bold text-white min-w-[12px] text-center">${count}</span>
                                    <button onclick="updateQuantity('${item.id}', 1)" class="w-5 h-5 rounded bg-brand-gold text-black font-bold flex items-center justify-center text-[10px]">
                                        <i class="fa-solid fa-plus"></i>
                                    </button>
                                </div>
                                <span class="text-xs font-bold text-white min-w-[35px] text-right font-serif">$${itemTotal}</span>
                            </div>
                        </div>
                    `;
                });
            }

            listContainer.innerHTML = html;
        }

        function renderCartModalItems() {
            const listContainer = document.getElementById('cartItemList');
            let html = '';
            const entries = Object.entries(cart);

            if (entries.length === 0) {
                html = `
                    <div class="text-center py-8 text-gray-400">
                        <i class="fa-solid fa-basket-shopping text-3xl mb-2 text-brand-gold/60"></i>
                        <p class="text-xs">${uiText[currentLang].emptyCartMsg}</p>
                    </div>
                `;
            } else {
                entries.forEach(([id, count]) => {
                    const item = getItemById(id);
                    if (!item) return;

                    const itemTotal = item.price * count;
                    html += `
                        <div class="flex items-center justify-between bg-black p-3 rounded-xl border border-brand-gold/20">
                            <div class="flex items-center gap-3">
                                <img src="${item.image}" alt="${item.names[currentLang]}" 
                                    onerror="this.onerror=null; this.src='https://placehold.co/100x100/181818/d4af37?text=Food';" 
                                    class="w-12 h-12 rounded-lg object-cover border border-brand-gold/30">
                                <div>
                                    <h5 class="text-xs font-bold text-white">${item.names[currentLang]}</h5>
                                    <p class="text-[11px] text-brand-gold font-serif">$${item.price} c/u</p>
                                </div>
                            </div>
                            <div class="flex items-center gap-3">
                                <div class="flex items-center bg-brand-card border border-brand-gold/30 rounded-lg p-1 gap-2">
                                    <button onclick="updateQuantity('${item.id}', -1)" class="w-6 h-6 rounded bg-brand-gold/20 text-brand-gold flex items-center justify-center text-xs">
                                        <i class="fa-solid fa-minus"></i>
                                    </button>
                                    <span class="text-xs font-bold text-white min-w-[12px] text-center">${count}</span>
                                    <button onclick="updateQuantity('${item.id}', 1)" class="w-6 h-6 rounded bg-brand-gold text-black font-bold flex items-center justify-center text-xs">
                                        <i class="fa-solid fa-plus"></i>
                                    </button>
                                </div>
                                <span class="text-xs font-bold text-white min-w-[45px] text-right font-serif">$${itemTotal}</span>
                            </div>
                        </div>
                    `;
                });
            }

            listContainer.innerHTML = html;
        }

        function toggleCartModal(show) {
            const modal = document.getElementById('cartModal');
            const content = document.getElementById('cartModalContent');
            if (show) {
                modal.classList.remove('pointer-events-none', 'opacity-0');
                content.classList.remove('translate-y-full');
            } else {
                modal.classList.add('opacity-0', 'pointer-events-none');
                content.classList.add('translate-y-full');
            }
        }

        function clearCart() {
            cart = {};
            renderMenu();
            updateCartUI();
            toggleCartModal(false);
        }

        function sendOrderToWhatsApp() {
            const entries = Object.entries(cart);
            if (entries.length === 0) return;

            let textMessage = "Hola La Cruderia! Me gustaría ordenar lo siguiente:\n\n";
            let total = 0;

            entries.forEach(([id, count]) => {
                const item = getItemById(id);
                if (item) {
                    const lineTotal = item.price * count;
                    total += lineTotal;
                    textMessage += `• ${count}x ${item.names[currentLang]} ($${lineTotal})\n`;
                }
            });

            textMessage += `\n*Total Estimado: $${total.toFixed(2)} CAD*\n`;
            textMessage += "Ubicación: 1121 Rue Bélanger, Montréal";

            const encodedMsg = encodeURIComponent(textMessage);
            window.open(`https://wa.me/5146416351?text=${encodedMsg}`, '_blank');
        }

        let toastTimeout;
        function showToast(msg) {
            const toast = document.getElementById('toast');
            document.getElementById('toastMsg').innerText = msg;
            toast.classList.remove('translate-x-full');
            clearTimeout(toastTimeout);
            toastTimeout = setTimeout(() => {
                toast.classList.add('translate-x-full');
            }, 2500);
        }
    </script>
</body>
</html>
