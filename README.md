<!DOCTYPE html>
<html lang="en" class="scroll-smooth">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>ARK TECHNOLOGY - Phones, Computers & Accessories | Kigali Rwanda</title>
    <script src="https://cdn.tailwindcss.com"></script>
    <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.4.0/css/all.min.css">
    <script>
        tailwind.config = {
            theme: {
                extend: {
                    colors: {
                        primary: 'var(--color-primary)',
                        secondary: 'var(--color-secondary)',
                        accent: 'var(--color-accent)',
                        success: 'var(--color-success)',
                        warning: 'var(--color-warning)',
                        danger: 'var(--color-danger)'
                    },
                    animation: {
                        'float': 'float 3s ease-in-out infinite',
                        'glow': 'glow 2s ease-in-out infinite alternate',
                        'bounce-slow': 'bounce 3s infinite',
                        'spin-slow': 'spin 3s linear infinite',
                        'pulse-slow': 'pulse 3s infinite'
                    }
                }
            }
        }
    </script>
    <style>
        :root {
            --color-primary: #1E40AF;
            --color-secondary: #DC2626;
            --color-accent: #059669;
            --color-success: #10B981;
            --color-warning: #F59E0B;
            --color-danger: #EF4444;
        }

        .theme-red {
            --color-primary: #DC2626;
            --color-secondary: #1E40AF;
            --color-accent: #059669;
        }

        .theme-green {
            --color-primary: #059669;
            --color-secondary: #8B5CF6;
            --color-accent: #F59E0B;
        }

        .theme-purple {
            --color-primary: #8B5CF6;
            --color-secondary: #DC2626;
            --color-accent: #059669;
        }

        @keyframes float {
            0%, 100% { transform: translateY(0px) rotateY(0deg); }
            50% { transform: translateY(-10px) rotateY(5deg); }
        }

        @keyframes glow {
            from { box-shadow: 0 0 5px var(--color-primary), 0 0 10px var(--color-primary), 0 0 15px var(--color-primary); }
            to { box-shadow: 0 0 10px var(--color-primary), 0 0 20px var(--color-primary), 0 0 30px var(--color-primary); }
        }

        .product-3d {
            perspective: 1000px;
            transform-style: preserve-3d;
            transition: all 0.5s ease;
        }

        .product-3d:hover {
            transform: rotateY(15deg) rotateX(5deg);
        }

        .product-card-3d {
            transform-style: preserve-3d;
            transition: all 0.3s ease;
        }

        .product-card-3d:hover {
            transform: translateZ(20px) rotateY(-5deg);
            box-shadow: 0 20px 40px rgba(0,0,0,0.15);
        }

        .glass-effect {
            background: rgba(255, 255, 255, 0.1);
            backdrop-filter: blur(10px);
            border: 1px solid rgba(255, 255, 255, 0.2);
        }

        .dark .glass-effect {
            background: rgba(0, 0, 0, 0.1);
            border: 1px solid rgba(255, 255, 255, 0.1);
        }

        .floating-widget {
            position: fixed;
            bottom: 20px;
            right: 20px;
            z-index: 1000;
        }

        .page-transition {
            opacity: 0;
            transform: translateY(20px);
            transition: all 0.5s ease;
        }

        .page-transition.active {
            opacity: 1;
            transform: translateY(0);
        }

        .product-image-3d {
            transition: all 0.3s ease;
            transform-style: preserve-3d;
        }

        .product-image-3d:hover {
            transform: rotateY(10deg) scale(1.05);
        }
    </style>
</head>
<body class="bg-white dark:bg-gray-900 text-gray-900 dark:text-white transition-all duration-300">
    <!-- Header -->
    <header class="sticky top-0 z-50 bg-white/90 dark:bg-gray-900/90 backdrop-blur-md shadow-lg border-b border-gray-200 dark:border-gray-700">
        <div class="container mx-auto px-4">
            <!-- Top Bar -->
            <div class="flex items-center justify-between py-2 text-sm border-b border-gray-100 dark:border-gray-800">
                <div class="flex items-center space-x-4">
                    <a href="tel:+250794779332" class="flex items-center space-x-1 text-primary hover:text-primary/80">
                        <i class="fas fa-phone animate-bounce-slow"></i>
                        <span>+250 794 779 332</span>
                    </a>
                    <div class="text-xs bg-primary/10 text-primary px-2 py-1 rounded">
                        <span id="selectedCurrency">RWF</span>
                        <i class="fas fa-exchange-alt ml-1 cursor-pointer" onclick="toggleCurrencyConverter()"></i>
                    </div>
                </div>
                <div class="flex items-center space-x-3">
                    <!-- Theme Selector -->
                    <div class="relative">
                        <button onclick="toggleThemeSelector()" class="p-2 text-gray-600 dark:text-gray-400 hover:text-primary">
                            <i class="fas fa-palette"></i>
                        </button>
                        <div id="themeSelector" class="hidden absolute top-full right-0 mt-2 p-3 bg-white dark:bg-gray-800 rounded-lg shadow-xl border border-gray-200 dark:border-gray-700 min-w-[200px]">
                            <div class="text-xs font-semibold mb-2">Choose Theme</div>
                            <div class="grid grid-cols-2 gap-2">
                                <button onclick="setTheme('default')" class="p-2 rounded flex items-center space-x-2 hover:bg-gray-100 dark:hover:bg-gray-700">
                                    <div class="w-4 h-4 bg-blue-600 rounded"></div>
                                    <span class="text-xs">Default</span>
                                </button>
                                <button onclick="setTheme('red')" class="p-2 rounded flex items-center space-x-2 hover:bg-gray-100 dark:hover:bg-gray-700">
                                    <div class="w-4 h-4 bg-red-600 rounded"></div>
                                    <span class="text-xs">Red</span>
                                </button>
                                <button onclick="setTheme('green')" class="p-2 rounded flex items-center space-x-2 hover:bg-gray-100 dark:hover:bg-gray-700">
                                    <div class="w-4 h-4 bg-green-600 rounded"></div>
                                    <span class="text-xs">Green</span>
                                </button>
                                <button onclick="setTheme('purple')" class="p-2 rounded flex items-center space-x-2 hover:bg-gray-100 dark:hover:bg-gray-700">
                                    <div class="w-4 h-4 bg-purple-600 rounded"></div>
                                    <span class="text-xs">Purple</span>
                                </button>
                            </div>
                        </div>
                    </div>
                    
                    <!-- Dark/Light Mode Toggle -->
                    <button onclick="toggleDarkMode()" class="p-2 text-gray-600 dark:text-gray-400 hover:text-primary">
                        <i id="themeIcon" class="fas fa-moon dark:fa-sun"></i>
                    </button>
                    
                    <!-- Social Links -->
                    <a href="https://wa.me/250794779332" class="text-green-600 hover:text-green-700">
                        <i class="fab fa-whatsapp text-lg"></i>
                    </a>
                    <a href="#" class="text-gray-600 dark:text-gray-400 hover:text-primary">
                        <i class="fab fa-instagram text-lg"></i>
                    </a>
                    <a href="#" class="text-gray-600 dark:text-gray-400 hover:text-primary">
                        <i class="fab fa-facebook text-lg"></i>
                    </a>
                </div>
            </div>
            
            <!-- Main Header -->
            <div class="flex items-center justify-between py-4">
                <div class="flex items-center space-x-4">
                    <button onclick="showPage('home')" class="text-2xl font-bold text-primary cursor-pointer hover:scale-105 transition-transform">
                        <i class="fas fa-mobile-alt mr-2 animate-glow"></i>ARK TECHNOLOGY
                    </button>
                </div>
                
                <!-- Navigation Menu -->
                <nav class="hidden lg:flex items-center space-x-6">
                    <button onclick="showPage('home')" class="nav-link text-gray-700 dark:text-gray-300 hover:text-primary font-medium">Home</button>
                    <button onclick="showPage('products')" class="nav-link text-gray-700 dark:text-gray-300 hover:text-primary font-medium">Products</button>
                    <button onclick="showPage('about')" class="nav-link text-gray-700 dark:text-gray-300 hover:text-primary font-medium">About</button>
                    <button onclick="showPage('contact')" class="nav-link text-gray-700 dark:text-gray-300 hover:text-primary font-medium">Contact</button>
                </nav>
                
                <!-- Search Bar -->
                <div class="hidden md:flex flex-1 max-w-2xl mx-8">
                    <div class="relative w-full">
                        <input type="text" id="searchInput" placeholder="Search phones, computers..." 
                               class="w-full px-4 py-2 text-base border border-gray-300 dark:border-gray-600 rounded-l-lg focus:outline-none focus:ring-2 focus:ring-primary dark:bg-gray-800">
                        <button onclick="searchProducts()" class="px-6 py-2 bg-primary text-white rounded-r-lg hover:bg-primary/90 transition-colors">
                            <i class="fas fa-search"></i>
                        </button>
                    </div>
                </div>
                
                <!-- User Actions -->
                <div class="flex items-center space-x-4">
                    <!-- Wishlist -->
                    <button onclick="toggleWishlist()" class="relative p-2 text-gray-600 dark:text-gray-400 hover:text-primary">
                        <i class="fas fa-heart text-xl"></i>
                        <span id="wishlistCount" class="absolute -top-1 -right-1 bg-secondary text-white text-xs rounded-full h-5 w-5 flex items-center justify-center hidden">0</span>
                    </button>
                    
                    <!-- Cart -->
                    <button onclick="toggleCart()" class="relative p-2 text-gray-600 dark:text-gray-400 hover:text-primary">
                        <i class="fas fa-shopping-cart text-xl"></i>
                        <span id="cartCount" class="absolute -top-1 -right-1 bg-primary text-white text-xs rounded-full h-5 w-5 flex items-center justify-center hidden">0</span>
                    </button>
                    
                    <!-- Mobile Menu Toggle -->
                    <button onclick="toggleMobileMenu()" class="lg:hidden p-2 text-gray-600 dark:text-gray-400">
                        <i class="fas fa-bars text-xl"></i>
                    </button>
                </div>
            </div>
            
            <!-- Mobile Search -->
            <div class="md:hidden pb-4">
                <div class="relative">
                    <input type="text" id="mobileSearchInput" placeholder="Search products..." 
                           class="w-full px-4 py-2 text-base border border-gray-300 dark:border-gray-600 rounded-lg focus:outline-none focus:ring-2 focus:ring-primary dark:bg-gray-800">
                    <button onclick="searchProducts()" class="absolute right-2 top-2 text-gray-400">
                        <i class="fas fa-search"></i>
                    </button>
                </div>
            </div>
        </div>
    </header>

    <!-- Mobile Navigation -->
    <div id="mobileMenu" class="hidden lg:hidden bg-white dark:bg-gray-900 border-b border-gray-200 dark:border-gray-700">
        <div class="container mx-auto px-4 py-4">
            <div class="space-y-2">
                <button onclick="showPage('home'); toggleMobileMenu()" class="w-full text-left px-3 py-2 text-gray-700 dark:text-gray-300 hover:text-primary hover:bg-gray-100 dark:hover:bg-gray-800 rounded">Home</button>
                <button onclick="showPage('products'); toggleMobileMenu()" class="w-full text-left px-3 py-2 text-gray-700 dark:text-gray-300 hover:text-primary hover:bg-gray-100 dark:hover:bg-gray-800 rounded">Products</button>
                <button onclick="showPage('about'); toggleMobileMenu()" class="w-full text-left px-3 py-2 text-gray-700 dark:text-gray-300 hover:text-primary hover:bg-gray-100 dark:hover:bg-gray-800 rounded">About</button>
                <button onclick="showPage('contact'); toggleMobileMenu()" class="w-full text-left px-3 py-2 text-gray-700 dark:text-gray-300 hover:text-primary hover:bg-gray-100 dark:hover:bg-gray-800 rounded">Contact</button>
            </div>
        </div>
    </div>

    <!-- Currency Converter Widget -->
    <div id="currencyConverter" class="hidden fixed top-20 right-4 z-50 bg-white dark:bg-gray-800 rounded-xl shadow-xl border border-gray-200 dark:border-gray-700 p-4 min-w-[250px]">
        <div class="flex items-center justify-between mb-3">
            <h3 class="font-semibold text-sm">Currency Converter</h3>
            <button onclick="toggleCurrencyConverter()" class="text-gray-400 hover:text-gray-600">
                <i class="fas fa-times"></i>
            </button>
        </div>
        <div class="space-y-3">
            <div>
                <label class="block text-xs text-gray-600 dark:text-gray-400 mb-1">From</label>
                <select id="fromCurrency" class="w-full px-3 py-2 text-sm border border-gray-300 dark:border-gray-600 rounded dark:bg-gray-700">
                    <option value="RWF">RWF - Rwandan Franc</option>
                    <option value="USD">USD - US Dollar</option>
                    <option value="EUR">EUR - Euro</option>
                </select>
            </div>
            <div>
                <label class="block text-xs text-gray-600 dark:text-gray-400 mb-1">To</label>
                <select id="toCurrency" class="w-full px-3 py-2 text-sm border border-gray-300 dark:border-gray-600 rounded dark:bg-gray-700">
                    <option value="USD">USD - US Dollar</option>
                    <option value="EUR">EUR - Euro</option>
                    <option value="RWF">RWF - Rwandan Franc</option>
                </select>
            </div>
            <button onclick="convertCurrency()" class="w-full bg-primary text-white py-2 rounded hover:bg-primary/90 text-sm">
                Convert Prices
            </button>
        </div>
    </div>

    <!-- Main Content Container -->
    <main id="mainContent" class="min-h-screen">
        <!-- Home Page -->
        <div id="homePage" class="page-content active">
            <!-- Hero Section -->
            <section class="relative bg-gradient-to-br from-primary via-blue-700 to-secondary text-white overflow-hidden">
                <div class="absolute inset-0">
                    <div class="absolute inset-0 bg-black/20"></div>
                    <div class="absolute top-10 left-10 w-32 h-32 bg-white/10 rounded-full animate-float"></div>
                    <div class="absolute bottom-10 right-10 w-24 h-24 bg-white/10 rounded-full animate-bounce-slow"></div>
                    <div class="absolute top-1/2 left-1/3 w-16 h-16 bg-accent/20 rounded-full animate-pulse-slow"></div>
                </div>
                
                <div class="container mx-auto px-4 py-16 md:py-24 relative z-10">
                    <div class="grid md:grid-cols-2 gap-12 items-center">
                        <div class="space-y-6">
                            <h1 class="text-4xl md:text-6xl font-bold leading-tight">
                                Premium Electronics
                                <span class="text-accent">in Kigali</span>
                            </h1>
                            <p class="text-xl opacity-90">Phones, Computers & Accessories with 3D product previews and unbeatable prices</p>
                            <div class="flex flex-col sm:flex-row gap-4">
                                <button onclick="showPage('products')" class="px-8 py-4 bg-white text-primary rounded-xl font-semibold hover:bg-gray-100 transition-all transform hover:scale-105">
                                    <i class="fas fa-cube mr-2"></i>Explore in 3D
                                </button>
                                <button onclick="contactWhatsApp()" class="px-8 py-4 border-2 border-white text-white rounded-xl font-semibold hover:bg-white hover:text-primary transition-all">
                                    <i class="fab fa-whatsapp mr-2"></i>Chat on WhatsApp
                                </button>
                            </div>
                        </div>
                        <div class="relative">
                            <div class="product-3d bg-white/10 rounded-2xl p-8 backdrop-blur-sm">
                                <div class="grid grid-cols-2 gap-6">
                                    <div class="text-center space-y-2">
                                        <div class="text-3xl font-bold">200+</div>
                                        <div class="text-sm opacity-90">Products</div>
                                    </div>
                                    <div class="text-center space-y-2">
                                        <div class="text-3xl font-bold">24/7</div>
                                        <div class="text-sm opacity-90">Support</div>
                                    </div>
                                    <div class="text-center space-y-2">
                                        <div class="text-3xl font-bold">100%</div>
                                        <div class="text-sm opacity-90">Original</div>
                                    </div>
                                    <div class="text-center space-y-2">
                                        <div class="text-3xl font-bold">Fast</div>
                                        <div class="text-sm opacity-90">Delivery</div>
                                    </div>
                                </div>
                            </div>
                        </div>
                    </div>
                </div>
            </section>

            <!-- Features Section -->
            <section class="py-16 bg-gray-50 dark:bg-gray-800">
                <div class="container mx-auto px-4">
                    <h2 class="text-3xl font-bold text-center mb-12">Why Choose ARK TECHNOLOGY?</h2>
                    <div class="grid md:grid-cols-3 gap-8">
                        <div class="text-center space-y-4 product-card-3d bg-white dark:bg-gray-900 p-8 rounded-2xl">
                            <div class="w-16 h-16 bg-primary/10 rounded-full flex items-center justify-center mx-auto">
                                <i class="fas fa-cube text-2xl text-primary"></i>
                            </div>
                            <h3 class="text-xl font-bold">3D Product Views</h3>
                            <p class="text-gray-600 dark:text-gray-400">Experience products in stunning 3D before you buy</p>
                        </div>
                        <div class="text-center space-y-4 product-card-3d bg-white dark:bg-gray-900 p-8 rounded-2xl">
                            <div class="w-16 h-16 bg-secondary/10 rounded-full flex items-center justify-center mx-auto">
                                <i class="fas fa-mobile-alt text-2xl text-secondary"></i>
                            </div>
                            <h3 class="text-xl font-bold">Mobile Money</h3>
                            <p class="text-gray-600 dark:text-gray-400">Pay easily with MTN Mobile Money or Airtel Money</p>
                        </div>
                        <div class="text-center space-y-4 product-card-3d bg-white dark:bg-gray-900 p-8 rounded-2xl">
                            <div class="w-16 h-16 bg-accent/10 rounded-full flex items-center justify-center mx-auto">
                                <i class="fas fa-shield-alt text-2xl text-accent"></i>
                            </div>
                            <h3 class="text-xl font-bold">Original Products</h3>
                            <p class="text-gray-600 dark:text-gray-400">100% genuine products with warranty</p>
                        </div>
                    </div>
                </div>
            </section>

            <!-- Featured Products -->
            <section class="py-16">
                <div class="container mx-auto px-4">
                    <h2 class="text-3xl font-bold text-center mb-12 flex items-center justify-center">
                        <i class="fas fa-fire text-secondary mr-3 animate-bounce"></i>
                        Hot Deals Today
                    </h2>
                    <div class="grid grid-cols-1 md:grid-cols-3 gap-8" id="featuredDeals">
                        <!-- Featured deals will be inserted here -->
                    </div>
                </div>
            </section>
        </div>

        <!-- Products Page -->
        <div id="productsPage" class="page-content hidden">
            <div class="container mx-auto px-4 py-8">
                <!-- Categories Navigation -->
                <nav class="bg-gray-50 dark:bg-gray-800 rounded-xl p-4 mb-8">
                    <div class="flex items-center justify-between">
                        <div class="flex items-center space-x-6 overflow-x-auto" id="categoryNav">
                            <!-- Categories will be inserted here -->
                        </div>
                        
                        <!-- Sort & Filter -->
                        <div class="flex items-center space-x-4">
                            <select id="sortSelect" onchange="sortProducts()" class="px-3 py-2 text-sm border border-gray-300 dark:border-gray-600 rounded-lg dark:bg-gray-700 focus:outline-none focus:ring-2 focus:ring-primary">
                                <option value="name">Sort by Name</option>
                                <option value="price-low">Price: Low to High</option>
                                <option value="price-high">Price: High to Low</option>
                                <option value="discount">Best Deals</option>
                                <option value="rating">Highest Rated</option>
                            </select>
                        </div>
                    </div>
                </nav>

                <!-- Products Grid -->
                <div class="flex items-center justify-between mb-6">
                    <h2 class="text-2xl font-bold">All Products</h2>
                    <div class="text-sm text-gray-600 dark:text-gray-400">
                        <span id="productCount">0</span> products found
                    </div>
                </div>
                
                <div class="grid grid-cols-1 sm:grid-cols-2 lg:grid-cols-3 xl:grid-cols-4 gap-6" id="productsGrid">
                    <!-- Products will be inserted here -->
                </div>
                
                <!-- Load More -->
                <div class="text-center mt-8">
                    <button id="loadMoreBtn" onclick="loadMoreProducts()" class="px-6 py-3 bg-primary text-white rounded-lg hover:bg-primary/90 transition-colors">
                        Load More Products
                    </button>
                </div>
            </div>
        </div>

        <!-- About Page -->
        <div id="aboutPage" class="page-content hidden">
            <div class="container mx-auto px-4 py-16">
                <div class="max-w-4xl mx-auto">
                    <h1 class="text-4xl font-bold text-center mb-8">About ARK TECHNOLOGY</h1>
                    
                    <div class="grid md:grid-cols-2 gap-12 items-center mb-16">
                        <div>
                            <h2 class="text-2xl font-bold mb-4">Your Technology Partner</h2>
                            <p class="text-gray-600 dark:text-gray-400 mb-4">
                                ARK TECHNOLOGY is Kigali's trusted source for quality phones, computers, and accessories. 
                                We specialize in bringing you the latest technology at competitive prices.
                            </p>
                            <p class="text-gray-600 dark:text-gray-400 mb-6">
                                From flagship smartphones to powerful laptops and essential accessories, 
                                we have everything you need to stay connected and productive.
                            </p>
                            <div class="space-y-3">
                                <div class="flex items-center space-x-3">
                                    <i class="fas fa-check-circle text-success"></i>
                                    <span>100% Original Products</span>
                                </div>
                                <div class="flex items-center space-x-3">
                                    <i class="fas fa-check-circle text-success"></i>
                                    <span>1 Year Warranty</span>
                                </div>
                                <div class="flex items-center space-x-3">
                                    <i class="fas fa-check-circle text-success"></i>
                                    <span>Expert Technical Support</span>
                                </div>
                            </div>
                        </div>
                        <div class="product-3d">
                            <div class="bg-gradient-to-br from-primary/10 to-secondary/10 rounded-2xl p-8">
                                <div class="grid grid-cols-2 gap-6 text-center">
                                    <div>
                                        <div class="text-3xl font-bold text-primary">200+</div>
                                        <div class="text-sm text-gray-600 dark:text-gray-400">Products</div>
                                    </div>
                                    <div>
                                        <div class="text-3xl font-bold text-secondary">2000+</div>
                                        <div class="text-sm text-gray-600 dark:text-gray-400">Customers</div>
                                    </div>
                                    <div>
                                        <div class="text-3xl font-bold text-accent">2+</div>
                                        <div class="text-sm text-gray-600 dark:text-gray-400">Years</div>
                                    </div>
                                    <div>
                                        <div class="text-3xl font-bold text-success">98%</div>
                                        <div class="text-sm text-gray-600 dark:text-gray-400">Satisfaction</div>
                                    </div>
                                </div>
                            </div>
                        </div>
                    </div>
                </div>
            </div>
        </div>

        <!-- Contact Page -->
        <div id="contactPage" class="page-content hidden">
            <div class="container mx-auto px-4 py-16">
                <div class="max-w-4xl mx-auto">
                    <h1 class="text-4xl font-bold text-center mb-8">Contact ARK TECHNOLOGY</h1>
                    
                    <div class="grid md:grid-cols-2 gap-12">
                        <!-- Contact Info -->
                        <div class="space-y-8">
                            <div>
                                <h2 class="text-2xl font-bold mb-6">Get in Touch</h2>
                                <p class="text-gray-600 dark:text-gray-400 mb-6">
                                    Ready to upgrade your tech? Contact us for the best deals on phones, computers, and accessories.
                                </p>
                            </div>
                            
                            <div class="space-y-4">
                                <div class="flex items-center space-x-4">
                                    <div class="w-12 h-12 bg-primary/10 rounded-lg flex items-center justify-center">
                                        <i class="fas fa-phone text-primary"></i>
                                    </div>
                                    <div>
                                        <h3 class="font-semibold">Phone</h3>
                                        <p class="text-gray-600 dark:text-gray-400">+250 794 779 332</p>
                                    </div>
                                </div>
                                
                                <div class="flex items-center space-x-4">
                                    <div class="w-12 h-12 bg-green-500/10 rounded-lg flex items-center justify-center">
                                        <i class="fab fa-whatsapp text-green-500"></i>
                                    </div>
                                    <div>
                                        <h3 class="font-semibold">WhatsApp</h3>
                                        <p class="text-gray-600 dark:text-gray-400">+250 794 779 332</p>
                                    </div>
                                </div>
                                
                                <div class="flex items-center space-x-4">
                                    <div class="w-12 h-12 bg-accent/10 rounded-lg flex items-center justify-center">
                                        <i class="fas fa-map-marker-alt text-accent"></i>
                                    </div>
                                    <div>
                                        <h3 class="font-semibold">Location</h3>
                                        <p class="text-gray-600 dark:text-gray-400">Kigali, Rwanda</p>
                                    </div>
                                </div>
                                
                                <div class="flex items-center space-x-4">
                                    <div class="w-12 h-12 bg-success/10 rounded-lg flex items-center justify-center">
                                        <i class="fas fa-clock text-success"></i>
                                    </div>
                                    <div>
                                        <h3 class="font-semibold">Business Hours</h3>
                                        <p class="text-gray-600 dark:text-gray-400">Mon - Sun: 8AM - 8PM</p>
                                    </div>
                                </div>
                            </div>
                        </div>
                        
                        <!-- Contact Form -->
                        <div class="product-card-3d bg-white dark:bg-gray-800 rounded-2xl p-8">
                            <form onsubmit="submitContactForm(event)" class="space-y-6">
                                <div>
                                    <label class="block text-sm font-medium mb-2">Name</label>
                                    <input type="text" required class="w-full px-4 py-3 text-base border border-gray-300 dark:border-gray-600 rounded-lg focus:outline-none focus:ring-2 focus:ring-primary dark:bg-gray-700">
                                </div>
                                <div>
                                    <label class="block text-sm font-medium mb-2">Phone</label>
                                    <input type="tel" required class="w-full px-4 py-3 text-base border border-gray-300 dark:border-gray-600 rounded-lg focus:outline-none focus:ring-2 focus:ring-primary dark:bg-gray-700">
                                </div>
                                <div>
                                    <label class="block text-sm font-medium mb-2">Product Interest</label>
                                    <select class="w-full px-4 py-3 text-base border border-gray-300 dark:border-gray-600 rounded-lg focus:outline-none focus:ring-2 focus:ring-primary dark:bg-gray-700">
                                        <option>Phones</option>
                                        <option>Computers</option>
                                        <option>Accessories</option>
                                        <option>General Inquiry</option>
                                    </select>
                                </div>
                                <div>
                                    <label class="block text-sm font-medium mb-2">Message</label>
                                    <textarea rows="4" required class="w-full px-4 py-3 text-base border border-gray-300 dark:border-gray-600 rounded-lg focus:outline-none focus:ring-2 focus:ring-primary dark:bg-gray-700"></textarea>
                                </div>
                                <button type="submit" class="w-full bg-primary text-white py-3 rounded-lg hover:bg-primary/90 transition-colors font-medium">
                                    Send Message
                                </button>
                            </form>
                        </div>
                    </div>
                </div>
            </div>
        </div>
    </main>

    <!-- Shopping Cart Sidebar -->
    <div id="cartSidebar" class="fixed inset-y-0 right-0 z-50 w-96 bg-white dark:bg-gray-900 shadow-2xl transform translate-x-full transition-transform duration-300">
        <div class="flex flex-col h-full">
            <div class="flex items-center justify-between p-4 border-b border-gray-200 dark:border-gray-700">
                <h3 class="text-lg font-semibold">Shopping Cart</h3>
                <button onclick="toggleCart()" class="p-2 text-gray-400 hover:text-gray-600">
                    <i class="fas fa-times"></i>
                </button>
            </div>
            
            <div class="flex-1 overflow-y-auto p-4">
                <div id="cartItems">
                    <div class="text-center text-gray-500 py-8">
                        <i class="fas fa-shopping-cart text-4xl mb-4"></i>
                        <p>Your cart is empty</p>
                    </div>
                </div>
            </div>
            
            <div class="border-t border-gray-200 dark:border-gray-700 p-4">
                <div class="flex items-center justify-between mb-4">
                    <span class="text-lg font-semibold">Total:</span>
                    <span id="cartTotal" class="text-lg font-bold text-primary">RWF 0</span>
                </div>
                <button onclick="contactWhatsApp()" class="w-full py-3 bg-green-500 text-white rounded-lg hover:bg-green-600 transition-colors mb-2">
                    <i class="fab fa-whatsapp mr-2"></i>Order via WhatsApp
                </button>
                <button onclick="showCheckoutModal()" class="w-full py-3 border border-gray-300 dark:border-gray-600 text-gray-700 dark:text-gray-300 rounded-lg hover:bg-gray-50 dark:hover:bg-gray-800 transition-colors">
                    Proceed to Checkout
                </button>
            </div>
        </div>
    </div>

    <!-- Wishlist Sidebar -->
    <div id="wishlistSidebar" class="fixed inset-y-0 right-0 z-50 w-96 bg-white dark:bg-gray-900 shadow-2xl transform translate-x-full transition-transform duration-300">
        <div class="flex flex-col h-full">
            <div class="flex items-center justify-between p-4 border-b border-gray-200 dark:border-gray-700">
                <h3 class="text-lg font-semibold">Wishlist</h3>
                <button onclick="toggleWishlist()" class="p-2 text-gray-400 hover:text-gray-600">
                    <i class="fas fa-times"></i>
                </button>
            </div>
            
            <div class="flex-1 overflow-y-auto p-4">
                <div id="wishlistItems">
                    <div class="text-center text-gray-500 py-8">
                        <i class="fas fa-heart text-4xl mb-4"></i>
                        <p>Your wishlist is empty</p>
                    </div>
                </div>
            </div>
        </div>
    </div>

    <!-- Product Quick View Modal -->
    <div id="quickViewModal" class="fixed inset-0 bg-black bg-opacity-50 z-50 hidden items-center justify-center p-4">
        <div class="bg-white dark:bg-gray-900 rounded-2xl max-w-6xl w-full max-h-[90vh] overflow-y-auto">
            <div class="p-6">
                <div class="flex items-center justify-between mb-4">
                    <h3 class="text-xl font-bold">Product Details</h3>
                    <button onclick="closeQuickView()" class="p-2 text-gray-400 hover:text-gray-600">
                        <i class="fas fa-times"></i>
                    </button>
                </div>
                
                <div id="quickViewContent">
                    <!-- Product details will be inserted here -->
                </div>
            </div>
        </div>
    </div>

    <!-- Checkout Modal -->
    <div id="checkoutModal" class="fixed inset-0 bg-black bg-opacity-50 z-50 hidden items-center justify-center p-4">
        <div class="bg-white dark:bg-gray-900 rounded-2xl max-w-4xl w-full max-h-[90vh] overflow-y-auto">
            <div class="p-6">
                <div class="flex items-center justify-between mb-6">
                    <h3 class="text-2xl font-bold">Checkout</h3>
                    <button onclick="closeCheckoutModal()" class="p-2 text-gray-400 hover:text-gray-600">
                        <i class="fas fa-times"></i>
                    </button>
                </div>
                
                <div class="grid md:grid-cols-2 gap-8">
                    <!-- Billing Info -->
                    <div>
                        <h4 class="text-lg font-semibold mb-4">Contact Information</h4>
                        <form id="checkoutForm" class="space-y-4">
                            <div>
                                <label class="block text-sm font-medium mb-1">Full Name</label>
                                <input type="text" required class="w-full px-3 py-2 text-base border border-gray-300 dark:border-gray-600 rounded-lg focus:outline-none focus:ring-2 focus:ring-primary dark:bg-gray-800">
                            </div>
                            <div>
                                <label class="block text-sm font-medium mb-1">Phone Number</label>
                                <input type="tel" required class="w-full px-3 py-2 text-base border border-gray-300 dark:border-gray-600 rounded-lg focus:outline-none focus:ring-2 focus:ring-primary dark:bg-gray-800">
                            </div>
                            <div>
                                <label class="block text-sm font-medium mb-1">Delivery Address</label>
                                <textarea rows="3" required class="w-full px-3 py-2 text-base border border-gray-300 dark:border-gray-600 rounded-lg focus:outline-none focus:ring-2 focus:ring-primary dark:bg-gray-800"></textarea>
                            </div>
                        </form>
                        
                        <!-- Payment Methods -->
                        <div class="mt-6">
                            <h4 class="text-lg font-semibold mb-4">Payment Method</h4>
                            <div class="space-y-3">
                                <label class="flex items-center space-x-3 p-3 border border-gray-300 dark:border-gray-600 rounded-lg cursor-pointer hover:bg-gray-50 dark:hover:bg-gray-800">
                                    <input type="radio" name="payment" value="mtn" class="text-primary" checked>
                                    <div class="flex items-center space-x-2">
                                        <i class="fas fa-mobile-alt text-yellow-500"></i>
                                        <span>MTN Mobile Money</span>
                                    </div>
                                </label>
                                <label class="flex items-center space-x-3 p-3 border border-gray-300 dark:border-gray-600 rounded-lg cursor-pointer hover:bg-gray-50 dark:hover:bg-gray-800">
                                    <input type="radio" name="payment" value="airtel" class="text-primary">
                                    <div class="flex items-center space-x-2">
                                        <i class="fas fa-mobile-alt text-red-500"></i>
                                        <span>Airtel Money</span>
                                    </div>
                                </label>
                                <label class="flex items-center space-x-3 p-3 border border-gray-300 dark:border-gray-600 rounded-lg cursor-pointer hover:bg-gray-50 dark:hover:bg-gray-800">
                                    <input type="radio" name="payment" value="cod" class="text-primary">
                                    <div class="flex items-center space-x-2">
                                        <i class="fas fa-money-bill text-green-500"></i>
                                        <span>Cash on Delivery</span>
                                    </div>
                                </label>
                            </div>
                        </div>
                    </div>
                    
                    <!-- Order Summary -->
                    <div>
                        <h4 class="text-lg font-semibold mb-4">Order Summary</h4>
                        <div class="bg-gray-50 dark:bg-gray-800 rounded-lg p-4">
                            <div id="checkoutItems" class="space-y-3 mb-4">
                                <!-- Checkout items will be inserted here -->
                            </div>
                            <div class="border-t border-gray-200 dark:border-gray-700 pt-4">
                                <div class="flex justify-between text-sm mb-2">
                                    <span>Subtotal:</span>
                                    <span id="checkoutSubtotal">RWF 0</span>
                                </div>
                                <div class="flex justify-between text-sm mb-2">
                                    <span>Delivery:</span>
                                    <span>Free in Kigali</span>
                                </div>
                                <div class="flex justify-between font-bold text-lg">
                                    <span>Total:</span>
                                    <span id="checkoutTotal">RWF 0</span>
                                </div>
                            </div>
                        </div>
                        
                        <button onclick="processOrder()" class="w-full mt-6 bg-primary text-white py-3 rounded-lg hover:bg-primary/90 transition-colors font-medium">
                            <i class="fas fa-check mr-2"></i>Place Order
                        </button>
                    </div>
                </div>
            </div>
        </div>
    </div>

    <!-- Cart Overlay -->
    <div id="cartOverlay" class="fixed inset-0 bg-black bg-opacity-50 z-40 hidden" onclick="toggleCart()"></div>
    <div id="wishlistOverlay" class="fixed inset-0 bg-black bg-opacity-50 z-40 hidden" onclick="toggleWishlist()"></div>

    <!-- Floating Widgets -->
    <div class="floating-widget space-y-4">
        <!-- WhatsApp Button -->
        <button onclick="contactWhatsApp()" class="bg-green-500 text-white p-4 rounded-full shadow-lg hover:bg-green-600 transition-all transform hover:scale-110 animate-bounce-slow">
            <i class="fab fa-whatsapp text-2xl"></i>
        </button>
        
        <!-- Back to Top Button -->
        <button onclick="scrollToTop()" class="bg-gray-600 text-white p-4 rounded-full shadow-lg hover:bg-gray-700 transition-all transform hover:scale-110">
            <i class="fas fa-arrow-up text-2xl"></i>
        </button>
    </div>

    <!-- Toast Notifications -->
    <div id="toastContainer" class="fixed top-20 right-4 z-60 space-y-2">
        <!-- Toast notifications will be inserted here -->
    </div>

    <!-- Footer -->
    <footer class="bg-gray-900 text-white py-12">
        <div class="container mx-auto px-4">
            <div class="grid md:grid-cols-4 gap-8">
                <div>
                    <h3 class="text-xl font-bold mb-4">ARK TECHNOLOGY</h3>
                    <p class="text-gray-400 mb-4">Your trusted technology partner in Kigali. Quality phones, computers, and accessories at competitive prices.</p>
                    <div class="flex space-x-3">
                        <a href="https://wa.me/250794779332" class="text-green-500 hover:text-green-400">
                            <i class="fab fa-whatsapp"></i>
                        </a>
                        <a href="#" class="text-gray-400 hover:text-white">
                            <i class="fab fa-instagram"></i>
                        </a>
                        <a href="#" class="text-gray-400 hover:text-white">
                            <i class="fab fa-facebook"></i>
                        </a>
                    </div>
                </div>
                
                <div>
                    <h4 class="font-semibold mb-4">Quick Links</h4>
                    <div class="space-y-2">
                        <button onclick="showPage('home')" class="block text-gray-400 hover:text-white">Home</button>
                        <button onclick="showPage('products')" class="block text-gray-400 hover:text-white">Products</button>
                        <button onclick="showPage('about')" class="block text-gray-400 hover:text-white">About</button>
                        <button onclick="showPage('contact')" class="block text-gray-400 hover:text-white">Contact</button>
                    </div>
                </div>
                
                <div>
                    <h4 class="font-semibold mb-4">Categories</h4>
                    <div class="space-y-2">
                        <button onclick="filterByCategory('PHONE')" class="block text-gray-400 hover:text-white">Phones</button>
                        <button onclick="filterByCategory('COMPUTER')" class="block text-gray-400 hover:text-white">Computers</button>
                        <button onclick="filterByCategory('ACCESSORY')" class="block text-gray-400 hover:text-white">Accessories</button>
                    </div>
                </div>
                
                <div>
                    <h4 class="font-semibold mb-4">Contact Info</h4>
                    <div class="space-y-2 text-gray-400">
                        <p><i class="fas fa-phone mr-2"></i>+250 794 779 332</p>
                        <p><i class="fab fa-whatsapp mr-2"></i>+250 794 779 332</p>
                        <p><i class="fas fa-map-marker-alt mr-2"></i>Kigali, Rwanda</p>
                    </div>
                </div>
            </div>
            
            <div class="border-t border-gray-800 mt-8 pt-8 text-center text-gray-400">
                <p>&copy; 2024 ARK TECHNOLOGY. All rights reserved.</p>
            </div>
        </div>
    </footer>

    <script>
        // Global state
        let allProducts = [];
        let filteredProducts = [];
        let currentProducts = [];
        let cart = [];
        let wishlist = [];
        let currentPage = 1;
        let currentPageName = 'home';
        const productsPerPage = 12;
        let currentTheme = 'default';
        let isDarkMode = false;
        let selectedCurrency = 'RWF';
        let exchangeRates = { RWF: 1, USD: 0.001, EUR: 0.0009 };

        // Real product data for ARK TECHNOLOGY
        const sampleProducts = [
            // Latest iPhones
            { id: 1, name: "iPhone 15 Pro Max", category: "PHONE", brand: "Apple", price: 1800000, originalPrice: 1850000, rating: 4.9, reviews: 245, image: "https://images.unsplash.com/photo-1695048133142-1a20484d2569?w=400&h=400&fit=crop", stock: 5 },
            { id: 2, name: "iPhone 15 Pro", category: "PHONE", brand: "Apple", price: 1600000, originalPrice: 1650000, rating: 4.8, reviews: 189, image: "https://images.unsplash.com/photo-1695048133142-1a20484d2569?w=400&h=400&fit=crop", stock: 8 },
            { id: 3, name: "iPhone 14 Pro Max", category: "PHONE", brand: "Apple", price: 1400000, originalPrice: 1450000, rating: 4.7, reviews: 324, image: "https://images.unsplash.com/photo-1663499482523-1c0c1bae4ce1?w=400&h=400&fit=crop", stock: 12 },
            { id: 4, name: "iPhone 13 Pro", category: "PHONE", brand: "Apple", price: 1100000, originalPrice: 1150000, rating: 4.6, reviews: 267, image: "https://images.unsplash.com/photo-1632661674596-df8be070a5c5?w=400&h=400&fit=crop", stock: 15 },
            { id: 5, name: "iPhone 12", category: "PHONE", brand: "Apple", price: 850000, originalPrice: 900000, rating: 4.5, reviews: 456, image: "https://images.unsplash.com/photo-1605787020600-b9ebd5df1d07?w=400&h=400&fit=crop", stock: 20 },
            
            // Samsung Galaxy Series
            { id: 6, name: "Samsung Galaxy S24 Ultra", category: "PHONE", brand: "Samsung", price: 1500000, originalPrice: 1550000, rating: 4.8, reviews: 198, image: "https://images.unsplash.com/photo-1610945265064-0e34e5519bbf?w=400&h=400&fit=crop", stock: 10 },
            { id: 7, name: "Samsung Galaxy S23", category: "PHONE", brand: "Samsung", price: 1100000, originalPrice: 1150000, rating: 4.6, reviews: 267, image: "https://images.unsplash.com/photo-1610945265064-0e34e5519bbf?w=400&h=400&fit=crop", stock: 18 },
            { id: 8, name: "Samsung Galaxy A54", category: "PHONE", brand: "Samsung", price: 450000, originalPrice: 480000, rating: 4.3, reviews: 156, image: "https://images.unsplash.com/photo-1610945265064-0e34e5519bbf?w=400&h=400&fit=crop", stock: 25 },
            { id: 9, name: "Samsung Galaxy A34", category: "PHONE", brand: "Samsung", price: 350000, originalPrice: 380000, rating: 4.2, reviews: 134, image: "https://images.unsplash.com/photo-1610945265064-0e34e5519bbf?w=400&h=400&fit=crop", stock: 30 },
            
            // Google Pixel
            { id: 10, name: "Google Pixel 8 Pro", category: "PHONE", brand: "Google", price: 1200000, originalPrice: 1250000, rating: 4.7, reviews: 89, image: "https://images.unsplash.com/photo-1598300042247-d088f8ab3a91?w=400&h=400&fit=crop", stock: 8 },
            { id: 11, name: "Google Pixel 7", category: "PHONE", brand: "Google", price: 750000, originalPrice: 800000, rating: 4.5, reviews: 123, image: "https://images.unsplash.com/photo-1598300042247-d088f8ab3a91?w=400&h=400&fit=crop", stock: 12 },
            
            // OnePlus
            { id: 12, name: "OnePlus 12", category: "PHONE", brand: "OnePlus", price: 980000, originalPrice: 1020000, rating: 4.6, reviews: 98, image: "https://images.unsplash.com/photo-1511707171634-5f897ff02aa9?w=400&h=400&fit=crop", stock: 15 },
            { id: 13, name: "OnePlus 11", category: "PHONE", brand: "OnePlus", price: 750000, originalPrice: 800000, rating: 4.4, reviews: 134, image: "https://images.unsplash.com/photo-1511707171634-5f897ff02aa9?w=400&h=400&fit=crop", stock: 20 },
            
            // MacBooks
            { id: 14, name: "MacBook Pro 16\" M3 Max", category: "COMPUTER", brand: "Apple", price: 4500000, originalPrice: 4600000, rating: 4.9, reviews: 145, image: "https://images.unsplash.com/photo-1541807084-5c52b6b3adef?w=400&h=400&fit=crop", stock: 3 },
            { id: 15, name: "MacBook Pro 14\" M3", category: "COMPUTER", brand: "Apple", price: 3200000, originalPrice: 3300000, rating: 4.8, reviews: 189, image: "https://images.unsplash.com/photo-1541807084-5c52b6b3adef?w=400&h=400&fit=crop", stock: 5 },
            { id: 16, name: "MacBook Air M2", category: "COMPUTER", brand: "Apple", price: 2200000, originalPrice: 2300000, rating: 4.7, reviews: 267, image: "https://images.unsplash.com/photo-1541807084-5c52b6b3adef?w=400&h=400&fit=crop", stock: 8 },
            { id: 17, name: "MacBook Air M1", category: "COMPUTER", brand: "Apple", price: 1800000, originalPrice: 1900000, rating: 4.6, reviews: 345, image: "https://images.unsplash.com/photo-1541807084-5c52b6b3adef?w=400&h=400&fit=crop", stock: 12 },
            
            // Dell Laptops
            { id: 18, name: "Dell XPS 13 Plus", category: "COMPUTER", brand: "Dell", price: 2800000, originalPrice: 2900000, rating: 4.5, reviews: 156, image: "https://images.unsplash.com/photo-1496181133206-80ce9b88a853?w=400&h=400&fit=crop", stock: 7 },
            { id: 19, name: "Dell Inspiron 15 3000", category: "COMPUTER", brand: "Dell", price: 850000, originalPrice: 900000, rating: 4.2, reviews: 98, image: "https://images.unsplash.com/photo-1496181133206-80ce9b88a853?w=400&h=400&fit=crop", stock: 15 },
            { id: 20, name: "Dell Latitude 7420", category: "COMPUTER", brand: "Dell", price: 1500000, originalPrice: 1600000, rating: 4.4, reviews: 78, image: "https://images.unsplash.com/photo-1496181133206-80ce9b88a853?w=400&h=400&fit=crop", stock: 10 },
            
            // HP Laptops
            { id: 21, name: "HP Spectre x360", category: "COMPUTER", brand: "HP", price: 2400000, originalPrice: 2500000, rating: 4.6, reviews: 134, image: "https://images.unsplash.com/photo-1484788984921-03950022c9ef?w=400&h=400&fit=crop", stock: 6 },
            { id: 22, name: "HP Pavilion 15", category: "COMPUTER", brand: "HP", price: 950000, originalPrice: 1000000, rating: 4.3, reviews: 156, image: "https://images.unsplash.com/photo-1484788984921-03950022c9ef?w=400&h=400&fit=crop", stock: 18 },
            { id: 23, name: "HP EliteBook 840", category: "COMPUTER", brand: "HP", price: 1800000, originalPrice: 1900000, rating: 4.5, reviews: 89, image: "https://images.unsplash.com/photo-1484788984921-03950022c9ef?w=400&h=400&fit=crop", stock: 12 },
            
            // Lenovo
            { id: 24, name: "Lenovo ThinkPad X1 Carbon", category: "COMPUTER", brand: "Lenovo", price: 2600000, originalPrice: 2700000, rating: 4.7, reviews: 123, image: "https://images.unsplash.com/photo-1588872657578-7efd1f1555ed?w=400&h=400&fit=crop", stock: 8 },
            { id: 25, name: "Lenovo IdeaPad 3", category: "COMPUTER", brand: "Lenovo", price: 750000, originalPrice: 800000, rating: 4.1, reviews: 167, image: "https://images.unsplash.com/photo-1588872657578-7efd1f1555ed?w=400&h=400&fit=crop", stock: 22 },
            
            // Gaming Laptops
            { id: 26, name: "ASUS ROG Strix G15", category: "COMPUTER", brand: "ASUS", price: 3200000, originalPrice: 3300000, rating: 4.8, reviews: 234, image: "https://images.unsplash.com/photo-1603302576837-37561b2e2302?w=400&h=400&fit=crop", stock: 5 },
            { id: 27, name: "MSI Gaming GF63", category: "COMPUTER", brand: "MSI", price: 1800000, originalPrice: 1900000, rating: 4.4, reviews: 145, image: "https://images.unsplash.com/photo-1603302576837-37561b2e2302?w=400&h=400&fit=crop", stock: 8 },
            
            // Phone Accessories
            { id: 28, name: "AirPods Pro 2nd Gen", category: "ACCESSORY", brand: "Apple", price: 450000, originalPrice: 480000, rating: 4.8, reviews: 345, image: "https://images.unsplash.com/photo-1606220945770-b5b6c2c6c8c0?w=400&h=400&fit=crop", stock: 25 },
            { id: 29, name: "AirPods 3rd Gen", category: "ACCESSORY", brand: "Apple", price: 350000, originalPrice: 380000, rating: 4.6, reviews: 267, image: "https://images.unsplash.com/photo-1606220945770-b5b6c2c6c8c0?w=400&h=400&fit=crop", stock: 30 },
            { id: 30, name: "Samsung Galaxy Buds2 Pro", category: "ACCESSORY", brand: "Samsung", price: 280000, originalPrice: 320000, rating: 4.5, reviews: 189, image: "https://images.unsplash.com/photo-1590658165737-15a047b3d3c6?w=400&h=400&fit=crop", stock: 35 },
            { id: 31, name: "Sony WH-1000XM5", category: "ACCESSORY", brand: "Sony", price: 650000, originalPrice: 700000, rating: 4.9, reviews: 456, image: "https://images.unsplash.com/photo-1546435770-a3e426bf472b?w=400&h=400&fit=crop", stock: 15 },
            { id: 32, name: "Anker PowerCore 10000", category: "ACCESSORY", brand: "Anker", price: 45000, originalPrice: 55000, rating: 4.7, reviews: 234, image: "https://images.unsplash.com/photo-1609592647095-89e1e76d8f02?w=400&h=400&fit=crop", stock: 50 },
            { id: 33, name: "Belkin 3-in-1 Wireless Charger", category: "ACCESSORY", brand: "Belkin", price: 120000, originalPrice: 140000, rating: 4.4, reviews: 145, image: "https://images.unsplash.com/photo-1556656793-08538906a9f8?w=400&h=400&fit=crop", stock: 20 },
            
            // Computer Accessories
            { id: 34, name: "Logitech MX Master 3S", category: "ACCESSORY", brand: "Logitech", price: 180000, originalPrice: 200000, rating: 4.8, reviews: 298, image: "https://images.unsplash.com/photo-1527814050087-3793815479db?w=400&h=400&fit=crop", stock: 25 },
            { id: 35, name: "Apple Magic Keyboard", category: "ACCESSORY", brand: "Apple", price: 220000, originalPrice: 250000, rating: 4.6, reviews: 167, image: "https://images.unsplash.com/photo-1587829741301-dc798b83add3?w=400&h=400&fit=crop", stock: 18 },
            { id: 36, name: "Samsung T7 Portable SSD 1TB", category: "ACCESSORY", brand: "Samsung", price: 280000, originalPrice: 320000, rating: 4.7, reviews: 189, image: "https://images.unsplash.com/photo-1597872200969-2b65d56bd16b?w=400&h=400&fit=crop", stock: 15 },
            { id: 37, name: "LG 27\" 4K Monitor", category: "ACCESSORY", brand: "LG", price: 850000, originalPrice: 900000, rating: 4.5, reviews: 123, image: "https://images.unsplash.com/photo-1527443224154-c4a3942d3acf?w=400&h=400&fit=crop", stock: 8 },
            { id: 38, name: "HyperX Gaming Headset", category: "ACCESSORY", brand: "HyperX", price: 180000, originalPrice: 220000, rating: 4.6, reviews: 234, image: "https://images.unsplash.com/photo-1599669454699-248893623440?w=400&h=400&fit=crop", stock: 22 }
        ];

        // Initialize the app
        function initializeApp() {
            allProducts = [...sampleProducts];
            filteredProducts = [...allProducts];
            currentProducts = filteredProducts.slice(0, productsPerPage);
            
            // Initialize dark mode based on system preference
            if (window.matchMedia && window.matchMedia('(prefers-color-scheme: dark)').matches) {
                isDarkMode = true;
                document.documentElement.classList.add('dark');
                document.getElementById('themeIcon').className = 'fas fa-sun';
            }
            
            // Listen for system theme changes
            window.matchMedia('(prefers-color-scheme: dark)').addEventListener('change', event => {
                if (event.matches) {
                    document.documentElement.classList.add('dark');
                    document.getElementById('themeIcon').className = 'fas fa-sun';
                } else {
                    document.documentElement.classList.remove('dark');
                    document.getElementById('themeIcon').className = 'fas fa-moon';
                }
            });
            
            renderCategories();
            renderProducts();
            renderFeaturedDeals();
            updateProductCount();
            showPage('home');
        }

        // Page Management
        function showPage(pageName) {
            // Hide all pages
            document.querySelectorAll('.page-content').forEach(page => {
                page.classList.add('hidden');
                page.classList.remove('active');
            });
            
            // Show selected page
            const targetPage = document.getElementById(pageName + 'Page');
            if (targetPage) {
                targetPage.classList.remove('hidden');
                setTimeout(() => {
                    targetPage.classList.add('active');
                }, 50);
                currentPageName = pageName;
                
                // Scroll to top
                window.scrollTo({ top: 0, behavior: 'smooth' });
                
                // Load page-specific content
                if (pageName === 'products') {
                    renderProducts();
                }
            }
        }

        // Theme Management
        function toggleDarkMode() {
            isDarkMode = !isDarkMode;
            const html = document.documentElement;
            const icon = document.getElementById('themeIcon');
            
            if (isDarkMode) {
                html.classList.add('dark');
                icon.className = 'fas fa-sun';
            } else {
                html.classList.remove('dark');
                icon.className = 'fas fa-moon';
            }
        }

        function toggleThemeSelector() {
            const selector = document.getElementById('themeSelector');
            selector.classList.toggle('hidden');
        }

        function setTheme(theme) {
            currentTheme = theme;
            document.body.className = document.body.className.replace(/theme-\w+/g, '');
            if (theme !== 'default') {
                document.body.classList.add(`theme-${theme}`);
            }
            toggleThemeSelector();
            showToast(`Theme changed to ${theme.charAt(0).toUpperCase() + theme.slice(1)}!`, 'success');
        }

        // Currency Management
        function toggleCurrencyConverter() {
            const converter = document.getElementById('currencyConverter');
            converter.classList.toggle('hidden');
        }

        function convertCurrency() {
            const fromCurrency = document.getElementById('fromCurrency').value;
            const toCurrency = document.getElementById('toCurrency').value;
            
            selectedCurrency = toCurrency;
            document.getElementById('selectedCurrency').textContent = toCurrency;
            
            // Update all prices on the page
            updateDisplayPrices();
            toggleCurrencyConverter();
            showToast(`Prices converted to ${toCurrency}!`, 'success');
        }

        function updateDisplayPrices() {
            renderProducts();
            updateCartDisplay();
        }

        function formatPrice(price, currency = selectedCurrency) {
            const convertedPrice = Math.round(price * exchangeRates[currency]);
            return `${currency} ${convertedPrice.toLocaleString()}`;
        }

        // Product Management
        function renderCategories() {
            const categories = [...new Set(allProducts.map(p => p.category))];
            const categoryNav = document.getElementById('categoryNav');
            
            if (!categoryNav) return;
            
            const categoryHTML = categories.map(category => 
                `<button onclick="filterByCategory('${category}')" class="whitespace-nowrap px-4 py-2 text-sm font-medium text-gray-700 dark:text-gray-300 hover:text-primary hover:bg-gray-100 dark:hover:bg-gray-700 rounded-lg transition-colors">
                    ${category === 'PHONE' ? 'Phones' : category === 'COMPUTER' ? 'Computers' : 'Accessories'}
                </button>`
            ).join('');
            
            categoryNav.innerHTML = `
                <button onclick="showAllProducts()" class="whitespace-nowrap px-4 py-2 text-sm font-medium text-primary bg-primary/10 rounded-lg">
                    All Products
                </button>
                ${categoryHTML}
            `;
        }

        function renderProducts() {
            const productsGrid = document.getElementById('productsGrid');
            if (!productsGrid) return;
            
            if (currentProducts.length === 0) {
                productsGrid.innerHTML = `
                    <div class="col-span-full text-center py-12">
                        <i class="fas fa-search text-4xl text-gray-400 mb-4"></i>
                        <p class="text-gray-500">No products found matching your criteria</p>
                    </div>
                `;
                return;
            }
            
            const productsHTML = currentProducts.map(product => {
                const discount = Math.round((1 - product.price / product.originalPrice) * 100);
                const isInWishlist = wishlist.some(item => item.id === product.id);
                
                return `
                    <div class="product-card-3d bg-white dark:bg-gray-800 rounded-xl shadow-md hover:shadow-2xl transition-all duration-500 overflow-hidden group">
                        <div class="relative">
                            <img src="${product.image}" alt="${product.name}" class="product-image-3d w-full h-48 object-cover group-hover:scale-110 transition-transform duration-500">
                            ${discount > 0 ? `<div class="absolute top-2 left-2 bg-secondary text-white px-2 py-1 rounded text-sm font-medium animate-pulse">-${discount}%</div>` : ''}
                            ${product.stock <= 5 ? `<div class="absolute top-2 right-2 bg-warning text-white px-2 py-1 rounded text-xs font-medium">Only ${product.stock} left!</div>` : ''}
                            
                            <!-- Action Buttons -->
                            <div class="absolute top-2 right-2 space-y-2 opacity-0 group-hover:opacity-100 transition-opacity duration-300">
                                <button onclick="toggleWishlistItem(${product.id})" class="p-2 rounded-full bg-white dark:bg-gray-800 shadow-md hover:bg-gray-50 dark:hover:bg-gray-700 transition-colors">
                                    <i class="fas fa-heart ${isInWishlist ? 'text-red-500' : 'text-gray-400'}"></i>
                                </button>
                                <button onclick="openQuickView(${product.id})" class="p-2 rounded-full bg-white dark:bg-gray-800 shadow-md hover:bg-gray-50 dark:hover:bg-gray-700 transition-colors">
                                    <i class="fas fa-eye text-gray-400"></i>
                                </button>
                            </div>
                            
                            <!-- 3D Effect on Hover -->
                            <div class="absolute inset-0 bg-black bg-opacity-0 group-hover:bg-opacity-20 transition-all duration-300 flex items-center justify-center opacity-0 group-hover:opacity-100">
                                <div class="transform translate-y-4 group-hover:translate-y-0 transition-transform duration-300">
                                    <button onclick="openQuickView(${product.id})" class="bg-white text-gray-900 px-4 py-2 rounded-lg font-medium shadow-lg">
                                        <i class="fas fa-cube mr-2"></i>View in 3D
                                    </button>
                                </div>
                            </div>
                        </div>
                        
                        <div class="p-4">
                            <div class="flex items-center justify-between mb-2">
                                <span class="text-xs text-primary font-medium">${product.brand}</span>
                                <div class="flex items-center space-x-1">
                                    ${renderStars(product.rating)}
                                    <span class="text-xs text-gray-500">(${product.reviews})</span>
                                </div>
                            </div>
                            
                            <h3 class="font-semibold text-gray-900 dark:text-white mb-2 line-clamp-2">${product.name}</h3>
                            
                            <div class="flex items-center space-x-2 mb-3">
                                <span class="text-lg font-bold text-primary">${formatPrice(product.price)}</span>
                                ${product.originalPrice > product.price ? `<span class="text-sm text-gray-500 line-through">${formatPrice(product.originalPrice)}</span>` : ''}
                            </div>
                            
                            <!-- Stock Indicator -->
                            <div class="mb-3">
                                <div class="flex items-center justify-between text-xs text-gray-500 mb-1">
                                    <span>Stock Level</span>
                                    <span>${product.stock} units</span>
                                </div>
                                <div class="w-full bg-gray-200 dark:bg-gray-700 rounded-full h-2">
                                    <div class="bg-success h-2 rounded-full" style="width: ${Math.min(product.stock / 30 * 100, 100)}%"></div>
                                </div>
                            </div>
                            
                            <div class="flex items-center space-x-2">
                                <button onclick="addToCart(${product.id})" class="flex-1 bg-primary text-white py-2 px-4 rounded-lg hover:bg-primary/90 transition-colors text-sm font-medium transform hover:scale-105">
                                    <i class="fas fa-cart-plus mr-1"></i>Add to Cart
                                </button>
                                <button onclick="buyNow(${product.id})" class="px-3 py-2 border border-primary text-primary rounded-lg hover:bg-primary hover:text-white transition-colors">
                                    <i class="fas fa-bolt"></i>
                                </button>
                            </div>
                        </div>
                    </div>
                `;
            }).join('');
            
            productsGrid.innerHTML = productsHTML;
            
            // Show/hide load more button
            const loadMoreBtn = document.getElementById('loadMoreBtn');
            if (loadMoreBtn) {
                if (currentProducts.length >= filteredProducts.length) {
                    loadMoreBtn.style.display = 'none';
                } else {
                    loadMoreBtn.style.display = 'inline-block';
                }
            }
        }

        function renderStars(rating) {
            const fullStars = Math.floor(rating);
            const hasHalfStar = rating % 1 >= 0.5;
            const emptyStars = 5 - fullStars - (hasHalfStar ? 1 : 0);
            
            let starsHTML = '';
            
            for (let i = 0; i < fullStars; i++) {
                starsHTML += '<i class="fas fa-star text-yellow-400"></i>';
            }
            
            if (hasHalfStar) {
                starsHTML += '<i class="fas fa-star-half-alt text-yellow-400"></i>';
            }
            
            for (let i = 0; i < emptyStars; i++) {
                starsHTML += '<i class="far fa-star text-gray-300"></i>';
            }
            
            return starsHTML;
        }

        function renderFeaturedDeals() {
            const featuredDeals = allProducts
                .filter(p => (p.originalPrice - p.price) / p.originalPrice > 0.05)
                .sort((a, b) => (b.originalPrice - b.price) - (a.originalPrice - a.price))
                .slice(0, 3);
            
            const featuredDealsContainer = document.getElementById('featuredDeals');
            if (!featuredDealsContainer) return;
            
            const dealsHTML = featuredDeals.map(product => {
                const discount = Math.round((1 - product.price / product.originalPrice) * 100);
                
                return `
                    <div class="product-card-3d bg-gradient-to-br from-secondary/10 to-accent/10 rounded-xl p-6 border border-secondary/20 hover:shadow-xl transition-all duration-300">
                        <div class="flex items-center justify-between mb-4">
                            <div class="bg-secondary text-white px-3 py-1 rounded-full text-sm font-bold animate-pulse">-${discount}%</div>
                            <div class="text-xs text-gray-600 dark:text-gray-400">Limited Time</div>
                        </div>
                        
                        <img src="${product.image}" alt="${product.name}" class="w-full h-32 object-cover rounded-lg mb-4 hover:scale-105 transition-transform duration-300">
                        
                        <h3 class="font-bold text-gray-900 dark:text-white mb-2">${product.name}</h3>
                        <div class="flex items-center space-x-1 mb-2">
                            ${renderStars(product.rating)}
                            <span class="text-xs text-gray-500">(${product.reviews})</span>
                        </div>
                        <div class="flex items-center space-x-2 mb-4">
                            <span class="text-xl font-bold text-secondary">${formatPrice(product.price)}</span>
                            <span class="text-sm text-gray-500 line-through">${formatPrice(product.originalPrice)}</span>
                        </div>
                        
                        <button onclick="addToCart(${product.id})" class="w-full bg-secondary text-white py-2 rounded-lg hover:bg-secondary/90 transition-colors font-medium transform hover:scale-105">
                            <i class="fas fa-cart-plus mr-2"></i>Add to Cart
                        </button>
                    </div>
                `;
            }).join('');
            
            featuredDealsContainer.innerHTML = dealsHTML;
        }

        // Search functionality
        function searchProducts() {
            const searchTerm = (document.getElementById('searchInput')?.value || document.getElementById('mobileSearchInput')?.value || '').toLowerCase();
            
            if (searchTerm.trim() === '') {
                filteredProducts = [...allProducts];
            } else {
                filteredProducts = allProducts.filter(product => 
                    product.name.toLowerCase().includes(searchTerm) ||
                    product.brand.toLowerCase().includes(searchTerm) ||
                    product.category.toLowerCase().includes(searchTerm)
                );
            }
            
            currentPage = 1;
            currentProducts = filteredProducts.slice(0, productsPerPage);
            renderProducts();
            updateProductCount();
            
            if (currentPageName !== 'products') {
                showPage('products');
            }
        }

        // Filter functions
        function filterByCategory(category) {
            filteredProducts = allProducts.filter(product => product.category === category);
            currentPage = 1;
            currentProducts = filteredProducts.slice(0, productsPerPage);
            renderProducts();
            updateProductCount();
            
            if (currentPageName !== 'products') {
                showPage('products');
            }
        }

        function showAllProducts() {
            filteredProducts = [...allProducts];
            currentPage = 1;
            currentProducts = filteredProducts.slice(0, productsPerPage);
            renderProducts();
            updateProductCount();
        }

        function sortProducts() {
            const sortValue = document.getElementById('sortSelect')?.value;
            
            switch (sortValue) {
                case 'price-low':
                    filteredProducts.sort((a, b) => a.price - b.price);
                    break;
                case 'price-high':
                    filteredProducts.sort((a, b) => b.price - a.price);
                    break;
                case 'discount':
                    filteredProducts.sort((a, b) => (b.originalPrice - b.price) - (a.originalPrice - a.price));
                    break;
                case 'rating':
                    filteredProducts.sort((a, b) => b.rating - a.rating);
                    break;
                default:
                    filteredProducts.sort((a, b) => a.name.localeCompare(b.name));
            }
            
            currentPage = 1;
            currentProducts = filteredProducts.slice(0, productsPerPage);
            renderProducts();
        }

        // Cart functionality
        function addToCart(productId) {
            const product = allProducts.find(p => p.id === productId);
            if (!product) return;
            
            const existingItem = cart.find(item => item.id === productId);
            
            if (existingItem) {
                if (existingItem.quantity < product.stock) {
                    existingItem.quantity += 1;
                    showToast(`${product.name} quantity updated in cart!`, 'success');
                } else {
                    showToast(`Sorry, only ${product.stock} units available!`, 'warning');
                    return;
                }
            } else {
                cart.push({ ...product, quantity: 1 });
                showToast(`${product.name} added to cart!`, 'success');
            }
            
            updateCartDisplay();
        }

        function removeFromCart(productId) {
            const product = allProducts.find(p => p.id === productId);
            cart = cart.filter(item => item.id !== productId);
            updateCartDisplay();
            showToast(`${product.name} removed from cart!`, 'info');
        }

        function updateQuantity(productId, change) {
            const item = cart.find(item => item.id === productId);
            const product = allProducts.find(p => p.id === productId);
            
            if (item) {
                const newQuantity = item.quantity + change;
                
                if (newQuantity <= 0) {
                    removeFromCart(productId);
                } else if (newQuantity <= product.stock) {
                    item.quantity = newQuantity;
                    updateCartDisplay();
                } else {
                    showToast(`Sorry, only ${product.stock} units available!`, 'warning');
                }
            }
        }

        function updateCartDisplay() {
            const cartItems = document.getElementById('cartItems');
            const cartCount = document.getElementById('cartCount');
            const cartTotal = document.getElementById('cartTotal');
            
            if (!cartItems || !cartCount || !cartTotal) return;
            
            if (cart.length === 0) {
                cartItems.innerHTML = `
                    <div class="text-center text-gray-500 py-8">
                        <i class="fas fa-shopping-cart text-4xl mb-4"></i>
                        <p>Your cart is empty</p>
                    </div>
                `;
                cartCount.classList.add('hidden');
                cartTotal.textContent = formatPrice(0);
                return;
            }
            
            const total = cart.reduce((sum, item) => sum + (item.price * item.quantity), 0);
            const totalItems = cart.reduce((sum, item) => sum + item.quantity, 0);
            
            cartCount.textContent = totalItems;
            cartCount.classList.remove('hidden');
            cartTotal.textContent = formatPrice(total);
            
            const cartHTML = cart.map(item => `
                <div class="flex items-center space-x-3 py-3 border-b border-gray-200 dark:border-gray-700">
                    <img src="${item.image}" alt="${item.name}" class="w-16 h-16 object-cover rounded">
                    <div class="flex-1">
                        <h4 class="font-medium text-sm">${item.name}</h4>
                        <p class="text-primary font-semibold">${formatPrice(item.price)}</p>
                        <div class="flex items-center space-x-1 text-xs">
                            ${renderStars(item.rating)}
                        </div>
                    </div>
                    <div class="flex items-center space-x-2">
                        <button onclick="updateQuantity(${item.id}, -1)" class="w-8 h-8 rounded-full border border-gray-300 dark:border-gray-600 flex items-center justify-center text-sm hover:bg-gray-100 dark:hover:bg-gray-700">-</button>
                        <span class="w-8 text-center text-sm">${item.quantity}</span>
                        <button onclick="updateQuantity(${item.id}, 1)" class="w-8 h-8 rounded-full border border-gray-300 dark:border-gray-600 flex items-center justify-center text-sm hover:bg-gray-100 dark:hover:bg-gray-700">+</button>
                    </div>
                    <button onclick="removeFromCart(${item.id})" class="text-red-500 hover:text-red-700">
                        <i class="fas fa-trash text-sm"></i>
                    </button>
                </div>
            `).join('');
            
            cartItems.innerHTML = cartHTML;
        }

        // Wishlist functionality
        function toggleWishlistItem(productId) {
            const product = allProducts.find(p => p.id === productId);
            const existingItem = wishlist.find(item => item.id === productId);
            
            if (existingItem) {
                wishlist = wishlist.filter(item => item.id !== productId);
                showToast(`${product.name} removed from wishlist`, 'info');
            } else {
                wishlist.push(product);
                showToast(`${product.name} added to wishlist!`, 'success');
            }
            
            updateWishlistDisplay();
            renderProducts(); // Re-render to update heart icons
        }

        function updateWishlistDisplay() {
            const wishlistItems = document.getElementById('wishlistItems');
            const wishlistCount = document.getElementById('wishlistCount');
            
            if (!wishlistItems || !wishlistCount) return;
            
            if (wishlist.length === 0) {
                wishlistItems.innerHTML = `
                    <div class="text-center text-gray-500 py-8">
                        <i class="fas fa-heart text-4xl mb-4"></i>
                        <p>Your wishlist is empty</p>
                    </div>
                `;
                wishlistCount.classList.add('hidden');
                return;
            }
            
            wishlistCount.textContent = wishlist.length;
            wishlistCount.classList.remove('hidden');
            
            const wishlistHTML = wishlist.map(item => `
                <div class="flex items-center space-x-3 py-3 border-b border-gray-200 dark:border-gray-700">
                    <img src="${item.image}" alt="${item.name}" class="w-16 h-16 object-cover rounded">
                    <div class="flex-1">
                        <h4 class="font-medium text-sm">${item.name}</h4>
                        <p class="text-primary font-semibold">${formatPrice(item.price)}</p>
                        <div class="flex items-center space-x-1 text-xs mb-2">
                            ${renderStars(item.rating)}
                            <span class="text-gray-500">(${item.reviews})</span>
                        </div>
                        <button onclick="addToCart(${item.id})" class="text-xs bg-primary text-white px-3 py-1 rounded hover:bg-primary/90">
                            Add to Cart
                        </button>
                    </div>
                    <button onclick="toggleWishlistItem(${item.id})" class="text-red-500 hover:text-red-700">
                        <i class="fas fa-heart"></i>
                    </button>
                </div>
            `).join('');
            
            wishlistItems.innerHTML = wishlistHTML;
        }

        // UI toggles
        function toggleCart() {
            const cartSidebar = document.getElementById('cartSidebar');
            const cartOverlay = document.getElementById('cartOverlay');
            const wishlistSidebar = document.getElementById('wishlistSidebar');
            const wishlistOverlay = document.getElementById('wishlistOverlay');
            
            if (!cartSidebar || !cartOverlay) return;
            
            // Close wishlist if open
            if (wishlistSidebar) wishlistSidebar.classList.add('translate-x-full');
            if (wishlistOverlay) wishlistOverlay.classList.add('hidden');
            
            cartSidebar.classList.toggle('translate-x-full');
            cartOverlay.classList.toggle('hidden');
        }

        function toggleWishlist() {
            const wishlistSidebar = document.getElementById('wishlistSidebar');
            const wishlistOverlay = document.getElementById('wishlistOverlay');
            const cartSidebar = document.getElementById('cartSidebar');
            const cartOverlay = document.getElementById('cartOverlay');
            
            if (!wishlistSidebar || !wishlistOverlay) return;
            
            // Close cart if open
            if (cartSidebar) cartSidebar.classList.add('translate-x-full');
            if (cartOverlay) cartOverlay.classList.add('hidden');
            
            wishlistSidebar.classList.toggle('translate-x-full');
            wishlistOverlay.classList.toggle('hidden');
        }

        function toggleMobileMenu() {
            const mobileMenu = document.getElementById('mobileMenu');
            if (mobileMenu) {
                mobileMenu.classList.toggle('hidden');
            }
        }

        // Quick view modal
        function openQuickView(productId) {
            const product = allProducts.find(p => p.id === productId);
            const modal = document.getElementById('quickViewModal');
            const content = document.getElementById('quickViewContent');
            
            if (!product || !modal || !content) return;
            
            const discount = Math.round((1 - product.price / product.originalPrice) * 100);
            const isInWishlist = wishlist.some(item => item.id === product.id);
            
            content.innerHTML = `
                <div class="grid md:grid-cols-2 gap-8">
                    <div class="relative product-3d">
                        <img src="${product.image}" alt="${product.name}" class="w-full h-96 object-cover rounded-xl">
                        ${discount > 0 ? `<div class="absolute top-4 left-4 bg-secondary text-white px-3 py-1 rounded text-sm font-medium animate-pulse">-${discount}%</div>` : ''}
                        ${product.stock <= 5 ? `<div class="absolute top-4 right-4 bg-warning text-white px-3 py-1 rounded text-sm font-medium">Only ${product.stock} left!</div>` : ''}
                    </div>
                    
                    <div class="space-y-6">
                        <div>
                            <div class="text-sm text-primary font-medium mb-2">${product.brand} • ${product.category === 'PHONE' ? 'Phone' : product.category === 'COMPUTER' ? 'Computer' : 'Accessory'}</div>
                            <h2 class="text-3xl font-bold text-gray-900 dark:text-white mb-4">${product.name}</h2>
                            
                            <div class="flex items-center space-x-2 mb-4">
                                ${renderStars(product.rating)}
                                <span class="text-sm text-gray-500">${product.rating} (${product.reviews} reviews)</span>
                            </div>
                        </div>
                        
                        <div class="flex items-center space-x-4">
                            <span class="text-4xl font-bold text-primary">${formatPrice(product.price)}</span>
                            ${product.originalPrice > product.price ? `<span class="text-xl text-gray-500 line-through">${formatPrice(product.originalPrice)}</span>` : ''}
                        </div>
                        
                        <!-- Stock Indicator -->
                        <div>
                            <div class="flex items-center justify-between text-sm text-gray-600 dark:text-gray-400 mb-2">
                                <span>Stock Level</span>
                                <span>${product.stock} units available</span>
                            </div>
                            <div class="w-full bg-gray-200 dark:bg-gray-700 rounded-full h-3">
                                <div class="bg-success h-3 rounded-full transition-all duration-300" style="width: ${Math.min(product.stock / 30 * 100, 100)}%"></div>
                            </div>
                        </div>
                        
                        <div class="space-y-4">
                            <div class="flex items-center text-success">
                                <i class="fas fa-check-circle mr-2"></i>
                                <span>In Stock</span>
                            </div>
                            <div class="flex items-center text-blue-600">
                                <i class="fas fa-shield-alt mr-2"></i>
                                <span>1 Year Warranty</span>
                            </div>
                            <div class="flex items-center text-purple-600">
                                <i class="fas fa-truck mr-2"></i>
                                <span>Free Delivery in Kigali</span>
                            </div>
                            <div class="flex items-center text-accent">
                                <i class="fas fa-mobile-alt mr-2"></i>
                                <span>Mobile Money Accepted</span>
                            </div>
                        </div>
                        
                        <!-- Quantity Selector -->
                        <div class="flex items-center space-x-4">
                            <label class="text-sm font-medium">Quantity:</label>
                            <div class="flex items-center space-x-2">
                                <button onclick="updateQuickViewQuantity(-1)" class="w-10 h-10 rounded-full border border-gray-300 dark:border-gray-600 flex items-center justify-center hover:bg-gray-100 dark:hover:bg-gray-700">-</button>
                                <span id="quickViewQuantity" class="w-12 text-center">1</span>
                                <button onclick="updateQuickViewQuantity(1)" class="w-10 h-10 rounded-full border border-gray-300 dark:border-gray-600 flex items-center justify-center hover:bg-gray-100 dark:hover:bg-gray-700">+</button>
                            </div>
                        </div>
                        
                        <div class="grid grid-cols-2 gap-4">
                            <button onclick="addMultipleToCart(${product.id}); closeQuickView()" class="bg-primary text-white py-3 px-6 rounded-xl hover:bg-primary/90 transition-colors font-medium transform hover:scale-105">
                                <i class="fas fa-cart-plus mr-2"></i>Add to Cart
                            </button>
                            <button onclick="buyNow(${product.id})" class="bg-success text-white py-3 px-6 rounded-xl hover:bg-success/90 transition-colors font-medium transform hover:scale-105">
                                <i class="fas fa-bolt mr-2"></i>Buy Now
                            </button>
                        </div>
                        
                        <div class="flex items-center space-x-4">
                            <button onclick="toggleWishlistItem(${product.id})" class="flex-1 p-3 border border-gray-300 dark:border-gray-600 rounded-xl hover:bg-gray-50 dark:hover:bg-gray-800 transition-colors">
                                <i class="fas fa-heart ${isInWishlist ? 'text-red-500' : 'text-gray-400'} mr-2"></i>
                                ${isInWishlist ? 'Remove from Wishlist' : 'Add to Wishlist'}
                            </button>
                            <button onclick="contactWhatsApp()" class="flex-1 p-3 bg-green-500 text-white rounded-xl hover:bg-green-600 transition-colors">
                                <i class="fab fa-whatsapp mr-2"></i>WhatsApp Us
                            </button>
                        </div>
                    </div>
                </div>
            `;
            
            modal.classList.remove('hidden');
            modal.classList.add('flex');
        }

        function updateQuickViewQuantity(change) {
            const quantitySpan = document.getElementById('quickViewQuantity');
            if (!quantitySpan) return;
            
            let currentQuantity = parseInt(quantitySpan.textContent);
            currentQuantity = Math.max(1, currentQuantity + change);
            quantitySpan.textContent = currentQuantity;
        }

        function addMultipleToCart(productId) {
            const quantity = parseInt(document.getElementById('quickViewQuantity')?.textContent || '1');
            
            for (let i = 0; i < quantity; i++) {
                addToCart(productId);
            }
        }

        function closeQuickView() {
            const modal = document.getElementById('quickViewModal');
            if (modal) {
                modal.classList.add('hidden');
                modal.classList.remove('flex');
            }
        }

        // Checkout functionality
        function showCheckoutModal() {
            if (cart.length === 0) {
                showToast('Your cart is empty!', 'warning');
                return;
            }
            
            const modal = document.getElementById('checkoutModal');
            const checkoutItems = document.getElementById('checkoutItems');
            const checkoutSubtotal = document.getElementById('checkoutSubtotal');
            const checkoutTotal = document.getElementById('checkoutTotal');
            
            if (!modal || !checkoutItems || !checkoutSubtotal || !checkoutTotal) return;
            
            const subtotal = cart.reduce((sum, item) => sum + (item.price * item.quantity), 0);
            
            checkoutSubtotal.textContent = formatPrice(subtotal);
            checkoutTotal.textContent = formatPrice(subtotal); // Free delivery
            
            const itemsHTML = cart.map(item => `
                <div class="flex items-center justify-between">
                    <div class="flex items-center space-x-3">
                        <img src="${item.image}" alt="${item.name}" class="w-12 h-12 object-cover rounded">
                        <div>
                            <h4 class="font-medium text-sm">${item.name}</h4>
                            <p class="text-xs text-gray-500">${item.brand}</p>
                        </div>
                    </div>
                    <div class="text-right">
                        <div class="font-medium">${formatPrice(item.price * item.quantity)}</div>
                        <div class="text-xs text-gray-500">Qty: ${item.quantity}</div>
                    </div>
                </div>
            `).join('');
            
            checkoutItems.innerHTML = itemsHTML;
            
            modal.classList.remove('hidden');
            modal.classList.add('flex');
        }

        function closeCheckoutModal() {
            const modal = document.getElementById('checkoutModal');
            if (modal) {
                modal.classList.add('hidden');
                modal.classList.remove('flex');
            }
        }

        function processOrder() {
            const form = document.getElementById('checkoutForm');
            const paymentMethod = document.querySelector('input[name="payment"]:checked');
            
            if (!form || !paymentMethod) {
                showToast('Please fill in all required fields and select a payment method!', 'warning');
                return;
            }
            
            // Simulate order processing
            showToast('Processing your order...', 'info');
            
            setTimeout(() => {
                const orderId = 'ARK-' + Date.now();
                showToast(`Order ${orderId} placed successfully! We will contact you shortly.`, 'success');
                
                // Clear cart
                cart = [];
                updateCartDisplay();
                closeCheckoutModal();
                
                // Redirect to WhatsApp with order details
                setTimeout(() => {
                    contactWhatsApp();
                }, 2000);
            }, 2000);
        }

        // Form handlers
        function submitContactForm(event) {
            event.preventDefault();
            showToast('Message sent successfully! We will get back to you soon.', 'success');
            event.target.reset();
        }

        // Utility functions
        function loadMoreProducts() {
            const nextProducts = filteredProducts.slice(currentProducts.length, currentProducts.length + productsPerPage);
            currentProducts = [...currentProducts, ...nextProducts];
            renderProducts();
        }

        function updateProductCount() {
            const productCountElement = document.getElementById('productCount');
            if (productCountElement) {
                productCountElement.textContent = filteredProducts.length;
            }
        }

        function scrollToTop() {
            window.scrollTo({ top: 0, behavior: 'smooth' });
        }

        function buyNow(productId) {
            addToCart(productId);
            setTimeout(() => {
                showCheckoutModal();
            }, 500);
        }

        function contactWhatsApp() {
            let message = "Hello ARK TECHNOLOGY! I'm interested in the following products:\n\n";
            
            if (cart.length > 0) {
                cart.forEach(item => {
                    message += `• ${item.name} (${item.brand}) - ${formatPrice(item.price)} x${item.quantity}\n`;
                });
                
                const total = cart.reduce((sum, item) => sum + (item.price * item.quantity), 0);
                message += `\nTotal: ${formatPrice(total)}\n\n`;
            }
            
            message += "Please provide more details about availability, delivery, and payment options.";
            
            const encodedMessage = encodeURIComponent(message);
            const whatsappUrl = `https://wa.me/250794779332?text=${encodedMessage}`;
            window.open(whatsappUrl, '_blank');
        }

        function showToast(message, type = 'info') {
            const toastContainer = document.getElementById('toastContainer');
            if (!toastContainer) return;
            
            const toastId = 'toast-' + Date.now();
            
            const colors = {
                success: 'bg-success',
                error: 'bg-danger',
                warning: 'bg-warning',
                info: 'bg-primary'
            };
            
            const icons = {
                success: 'fas fa-check-circle',
                error: 'fas fa-exclamation-circle',
                warning: 'fas fa-exclamation-triangle',
                info: 'fas fa-info-circle'
            };
            
            const toast = document.createElement('div');
            toast.id = toastId;
            toast.className = `${colors[type]} text-white px-4 py-3 rounded-xl shadow-lg flex items-center space-x-2 transform translate-x-full transition-transform duration-300 max-w-sm`;
            toast.innerHTML = `
                <i class="${icons[type]}"></i>
                <span class="flex-1">${message}</span>
                <button onclick="removeToast('${toastId}')" class="ml-2 text-white hover:text-gray-200">
                    <i class="fas fa-times"></i>
                </button>
            `;
            
            toastContainer.appendChild(toast);
            
            // Animate in
            setTimeout(() => {
                toast.classList.remove('translate-x-full');
            }, 100);
            
            // Auto remove after 5 seconds
            setTimeout(() => {
                removeToast(toastId);
            }, 5000);
        }

        function removeToast(toastId) {
            const toast = document.getElementById(toastId);
            if (toast) {
                toast.classList.add('translate-x-full');
                setTimeout(() => {
                    toast.remove();
                }, 300);
            }
        }

        // Initialize app when page loads
        document.addEventListener('DOMContentLoaded', initializeApp);

        // Search on Enter key
        document.addEventListener('keypress', function(e) {
            if (e.key === 'Enter') {
                const activeElement = document.activeElement;
                if (activeElement && (activeElement.id === 'searchInput' || activeElement.id === 'mobileSearchInput')) {
                    searchProducts();
                }
            }
        });

        // Close modals on Escape key
        document.addEventListener('keydown', function(e) {
            if (e.key === 'Escape') {
                closeQuickView();
                closeCheckoutModal();
                
                const cartSidebar = document.getElementById('cartSidebar');
                const wishlistSidebar = document.getElementById('wishlistSidebar');
                const cartOverlay = document.getElementById('cartOverlay');
                const wishlistOverlay = document.getElementById('wishlistOverlay');
                
                if (cartSidebar) cartSidebar.classList.add('translate-x-full');
                if (wishlistSidebar) wishlistSidebar.classList.add('translate-x-full');
                if (cartOverlay) cartOverlay.classList.add('hidden');
                if (wishlistOverlay) wishlistOverlay.classList.add('hidden');
            }
        });

        // Close dropdowns when clicking outside
        document.addEventListener('click', function(e) {
            const themeSelector = document.getElementById('themeSelector');
            const currencyConverter = document.getElementById('currencyConverter');
            
            if (themeSelector && !themeSelector.closest('div').contains(e.target)) {
                themeSelector.classList.add('hidden');
            }
            
            if (currencyConverter && !currencyConverter.closest('div').contains(e.target) && !e.target.closest('[onclick="toggleCurrencyConverter()"]')) {
                currencyConverter.classList.add('hidden');
            }
        });
    </script>
</body>
</html>
