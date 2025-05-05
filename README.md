{{-- home.blade.php --}}
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>CodeVault - Premium Code Solutions</title>
    <script src="https://cdn.jsdelivr.net/npm/@tailwindcss/browser@4"></script>
    <link href="{{ asset('css/app.css') }}" rel="stylesheet">
    <script src="{{ asset('js/app.js') }}" defer></script>x
</head>
<body class="flex min-h-screen flex-col bg-black text-white">
    <header class="sticky top-0 z-40 w-full border-b border-zinc-800 bg-black/95 backdrop-blur">
        <div class="container flex h-16 items-center justify-between">
            <div class="flex items-center gap-2">
                <svg xmlns="http://www.w3.org/2000/svg" class="h-8 w-8 text-emerald-500" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2" stroke-linecap="round" stroke-linejoin="round">
                    <path d="m18 16 4-4-4-4"></path>
                    <path d="m6 8-4 4 4 4"></path>
                    <path d="m14.5 4-5 16"></path>
                </svg>
                <span class="text-xl font-bold">CodeVault</span>
            </div>
            <nav class="hidden md:flex items-center gap-6">
                <a href="#" class="text-sm font-medium text-zinc-400 hover:text-white">Browse</a>
                <a href="#" class="text-sm font-medium text-zinc-400 hover:text-white">Categories</a>
                <a href="#" class="text-sm font-medium text-zinc-400 hover:text-white">Pricing</a>
                <a href="#" class="text-sm font-medium text-zinc-400 hover:text-white">About</a>
            </nav>
            <div class="flex items-center gap-4">
                <div class="hidden md:flex relative rounded-full bg-zinc-900 px-3 py-1.5">
                    <svg xmlns="http://www.w3.org/2000/svg" class="h-4 w-4 text-zinc-500" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2" stroke-linecap="round" stroke-linejoin="round">
                        <circle cx="11" cy="11" r="8"></circle>
                        <path d="m21 21-4.3-4.3"></path>
                    </svg>
                    <input
                        type="text"
                        placeholder="Search scripts..."
                        class="ml-2 bg-transparent text-sm outline-none placeholder:text-zinc-500"
                    >
                </div>
                <button class="hidden md:flex border-zinc-800 bg-zinc-950 text-white hover:bg-zinc-900 hover:text-white border rounded-md px-4 py-2 text-sm font-medium">
                    Sign In
                </button>
                <button class="bg-emerald-600 hover:bg-emerald-700 rounded-md px-4 py-2 text-sm font-medium text-white">
                    Get Started
                </button>
            </div>
        </div>
    </header>

    <main class="flex-1">
        {{-- Hero Section --}}
        <section class="relative overflow-hidden py-20 md:py-32 border-b border-zinc-800">
            <div class="absolute inset-0 bg-[radial-gradient(circle_at_30%_20%,rgba(16,185,129,0.2),transparent_50%)]"></div>
            <div class="container relative z-10 mx-auto px-4 text-center">
                <span class="inline-flex items-center rounded-md bg-emerald-950 px-2 py-1 text-xs font-medium text-emerald-400 mb-4">
                    Premium Code Marketplace
                </span>
                <h1 class="mb-6 text-4xl font-extrabold tracking-tight md:text-6xl lg:text-7xl">
                    Premium Code <span class="text-emerald-500">Solutions</span> for Developers
                </h1>
                <p class="mx-auto mb-8 max-w-2xl text-lg text-zinc-400 md:text-xl">
                    Discover high-quality, ready-to-use code snippets, scripts, and full applications built by expert
                    developers.
                </p>
                <div class="flex flex-col sm:flex-row items-center justify-center gap-4">
                    <button class="bg-emerald-600 hover:bg-emerald-700 rounded-md px-6 py-3 text-base font-medium text-white">
                        Browse Marketplace
                    </button>
                    <button class="border-zinc-800 bg-zinc-950 text-white hover:bg-zinc-900 hover:text-white border rounded-md px-6 py-3 text-base font-medium">
                        Sell Your Code
                    </button>
                </div>
                <div class="mt-16 relative mx-auto max-w-5xl rounded-lg border border-zinc-800 bg-zinc-950 shadow-2xl">
                    <div class="flex items-center border-b border-zinc-800 px-4 py-2">
                        <div class="flex space-x-2">
                            <div class="h-3 w-3 rounded-full bg-red-500"></div>
                            <div class="h-3 w-3 rounded-full bg-yellow-500"></div>
                            <div class="h-3 w-3 rounded-full bg-green-500"></div>
                        </div>
                        <div class="mx-auto text-sm text-zinc-400">Premium React Dashboard Template</div>
                    </div>
                    <div class="overflow-hidden rounded-b-lg">
                        <img
                            src="{{ asset('images/placeholder.jpg') }}"
                            alt="Code preview"
                            class="w-full object-cover"
                            style="height: 600px;"
                        >
                    </div>
                </div>
            </div>
        </section>

        {{-- Featured Products --}}
        <section class="py-20 border-b border-zinc-800">
            <div class="container">
                <div class="mb-12 text-center">
                    <h2 class="text-3xl font-bold tracking-tight md:text-4xl">Featured Products</h2>
                    <p class="mt-4 text-zinc-400">Discover our most popular code solutions</p>
                </div>
                
                <div x-data="{ tab: 'all' }">
                    <div class="flex justify-center mb-8">
                        <div class="inline-flex rounded-md bg-zinc-900 p-1">
                            <button 
                                @click="tab = 'all'" 
                                :class="{ 'bg-white text-zinc-900': tab === 'all', 'text-zinc-400': tab !== 'all' }"
                                class="px-3 py-1.5 text-sm font-medium rounded-md"
                            >All</button>
                            <button 
                                @click="tab = 'scripts'" 
                                :class="{ 'bg-white text-zinc-900': tab === 'scripts', 'text-zinc-400': tab !== 'scripts' }"
                                class="px-3 py-1.5 text-sm font-medium rounded-md"
                            >Scripts</button>
                            <button 
                                @click="tab = 'templates'" 
                                :class="{ 'bg-white text-zinc-900': tab === 'templates', 'text-zinc-400': tab !== 'templates' }"
                                class="px-3 py-1.5 text-sm font-medium rounded-md"
                            >Templates</button>
                            <button 
                                @click="tab = 'plugins'" 
                                :class="{ 'bg-white text-zinc-900': tab === 'plugins', 'text-zinc-400': tab !== 'plugins' }"
                                class="px-3 py-1.5 text-sm font-medium rounded-md"
                            >Plugins</button>
                        </div>
                    </div>
                    
                    <div x-show="tab === 'all'" class="grid gap-6 sm:grid-cols-2 lg:grid-cols-3">
                        @foreach ($featuredProducts as $product)
                            @include('components.product-card', ['product' => $product])
                        @endforeach
                    </div>
                    
                    <div x-show="tab === 'scripts'" class="grid gap-6 sm:grid-cols-2 lg:grid-cols-3">
                        @foreach ($featuredProducts as $product)
                            @if ($product['type'] === 'Script')
                                @include('components.product-card', ['product' => $product])
                            @endif
                        @endforeach
                    </div>
                    
                    <div x-show="tab === 'templates'" class="grid gap-6 sm:grid-cols-2 lg:grid-cols-3">
                        @foreach ($featuredProducts as $product)
                            @if ($product['type'] === 'Template')
                                @include('components.product-card', ['product' => $product])
                            @endif
                        @endforeach
                    </div>
                    
                    <div x-show="tab === 'plugins'" class="grid gap-6 sm:grid-cols-2 lg:grid-cols-3">
                        @foreach ($featuredProducts as $product)
                            @if ($product['type'] === 'Plugin')
                                @include('components.product-card', ['product' => $product])
                            @endif
                        @endforeach
                    </div>
                </div>
                
                <div class="mt-12 text-center">
                    <button class="border-zinc-800 bg-zinc-950 text-white hover:bg-zinc-900 hover:text-white border rounded-md px-4 py-2 text-sm font-medium">
                        View All Products
                    </button>
                </div>
            </div>
        </section>

        {{-- Why Choose Us --}}
        <section class="py-20 border-b border-zinc-800">
            <div class="container">
                <div class="mb-12 text-center">
                    <h2 class="text-3xl font-bold tracking-tight md:text-4xl">Why Choose CodeVault</h2>
                    <p class="mt-4 text-zinc-400">Premium features for developers who value quality and time</p>
                </div>
                <div class="grid gap-8 md:grid-cols-2 lg:grid-cols-3">
                    @include('components.feature-card', [
                        'icon' => 'zap',
                        'title' => 'Ready to Use',
                        'description' => 'All code is thoroughly tested and ready to implement in your projects immediately.'
                    ])
                    
                    @include('components.feature-card', [
                        'icon' => 'file-code',
                        'title' => 'Clean Code',
                        'description' => 'Well-structured, documented code following best practices and coding standards.'
                    ])
                    
                    @include('components.feature-card', [
                        'icon' => 'credit-card',
                        'title' => 'Secure Payments',
                        'description' => 'Safe transactions with multiple payment options and money-back guarantee.'
                    ])
                    
                    @include('components.feature-card', [
                        'icon' => 'download',
                        'title' => 'Instant Download',
                        'description' => 'Get immediate access to your purchased code with no waiting time.'
                    ])
                    
                    @include('components.feature-card', [
                        'icon' => 'layers',
                        'title' => 'Regular Updates',
                        'description' => 'Free updates and improvements to keep your code current with latest standards.'
                    ])
                    
                    @include('components.feature-card', [
                        'icon' => 'github',
                        'title' => 'Developer Support',
                        'description' => 'Direct access to the code author for questions and implementation help.'
                    ])
                </div>
            </div>
        </section>

        {{-- Testimonials --}}
        <section class="py-20 border-b border-zinc-800">
            <div class="container">
                <div class="mb-12 text-center">
                    <h2 class="text-3xl font-bold tracking-tight md:text-4xl">Trusted by Developers</h2>
                    <p class="mt-4 text-zinc-400">See what our customers have to say about our products</p>
                </div>
                <div class="grid gap-8 md:grid-cols-2 lg:grid-cols-3">
                    @include('components.testimonial-card', [
                        'quote' => 'The React dashboard template saved me weeks of development time. Clean code and excellent documentation!',
                        'author' => 'Sarah Johnson',
                        'role' => 'Frontend Developer',
                        'avatar' => 'images/placeholder.jpg'
                    ])
                    
                    @include('components.testimonial-card', [
                        'quote' => 'I\'ve purchased multiple scripts from CodeVault and they\'ve all been top quality. Customer support is excellent too.',
                        'author' => 'Michael Chen',
                        'role' => 'Full Stack Developer',
                        'avatar' => 'images/placeholder.jpg'
                    ])
                    
                    @include('components.testimonial-card', [
                        'quote' => 'As a startup founder with limited technical resources, these code solutions have been invaluable for our MVP.',
                        'author' => 'Jessica Williams',
                        'role' => 'Startup Founder',
                        'avatar' => 'images/placeholder.jpg'
                    ])
                </div>
            </div>
        </section>

        {{-- CTA Section --}}
        <section class="py-20">
            <div class="container">
                <div class="relative overflow-hidden rounded-2xl bg-gradient-to-r from-emerald-950 to-zinc-900 p-8 md:p-12">
                    <div class="absolute top-0 right-0 -mt-16 -mr-16 h-64 w-64 rounded-full bg-emerald-500/20 blur-3xl"></div>
                    <div class="relative z-10 flex flex-col items-center text-center md:flex-row md:text-left">
                        <div class="md:w-2/3">
                            <h2 class="text-3xl font-bold tracking-tight md:text-4xl">Ready to elevate your development?</h2>
                            <p class="mt-4 text-lg text-zinc-300">
                                Join thousands of developers who are shipping faster with our premium code solutions.
                            </p>
                        </div>
                        <div class="mt-8 flex flex-shrink-0 md:mt-0 md:ml-auto">
                            <button class="bg-emerald-600 hover:bg-emerald-700 rounded-md px-6 py-3 text-base font-medium text-white">
                                Get Started Today
                            </button>
                        </div>
                    </div>
                </div>
            </div>
        </section>
    </main>

    <footer class="border-t border-zinc-800 bg-zinc-950 py-12">
        <div class="container">
            <div class="flex flex-col items-center justify-between gap-6 md:flex-row">
                <div class="flex items-center gap-2">
                    <svg xmlns="http://www.w3.org/2000/svg" class="h-8 w-8 text-emerald-500" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2" stroke-linecap="round" stroke-linejoin="round">
                        <path d="m18 16 4-4-4-4"></path>
                        <path d="m6 8-4 4 4 4"></path>
                        <path d="m14.5 4-5 16"></path>
                    </svg>
                    <span class="text-xl font-bold">CodeVault</span>
                </div>
                <nav class="flex flex-wrap justify-center gap-x-8 gap-y-4">
                    <a href="#" class="text-sm text-zinc-400 hover:text-white">Browse</a>
                    <a href="#" class="text-sm text-zinc-400 hover:text-white">Categories</a>
                    <a href="#" class="text-sm text-zinc-400 hover:text-white">Pricing</a>
                    <a href="#" class="text-sm text-zinc-400 hover:text-white">About</a>
                    <a href="#" class="text-sm text-zinc-400 hover:text-white">Contact</a>
                </nav>
                <div class="flex items-center gap-4">
                    <a href="#" class="text-zinc-400 hover:text-white">
                        <svg xmlns="http://www.w3.org/2000/svg" class="h-5 w-5" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2" stroke-linecap="round" stroke-linejoin="round">
                            <path d="M15 22v-4a4.8 4.8 0 0 0-1-3.5c3 0 6-2 6-5.5.08-1.25-.27-2.48-1-3.5.28-1.15.28-2.35 0-3.5 0 0-1 0-3 1.5-2.64-.5-5.36-.5-8 0C6 2 5 2 5 2c-.3 1.15-.3 2.35 0 3.5A5.403 5.403 0 0 0 4 9c0 3.5 3 5.5 6 5.5-.39.49-.68 1.05-.85 1.65-.17.6-.22 1.23-.15 1.85v4"></path>
                            <path d="M9 18c-4.51 2-5-2-7-2"></path>
                        </svg>
                        <span class="sr-only">GitHub</span>
                    </a>
                    <a href="#" class="text-zinc-400 hover:text-white">
                        <svg xmlns="http://www.w3.org/2000/svg" class="h-5 w-5" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2" stroke-linecap="round" stroke-linejoin="round">
                            <circle cx="12" cy="12" r="10"></circle>
                            <path d="M2 12h2a8 8 0 0 1 8-8v2m10 6h-2a8 8 0 0 1-8 8v-2"></path>
                        </svg>
                        <span class="sr-only">Website</span>
                    </a>
                </div>
            </div>
            <div class="mt-8 border-t border-zinc-800 pt-8 text-center text-sm text-zinc-500">
                <p>© {{ date('Y') }} CodeVault. All rights reserved.</p>
            </div>
        </div>
    </footer>

    <script src="https://cdn.jsdelivr.net/npm/alpinejs@3.x.x/dist/cdn.min.js"></script>
</body>
</html>
