additional adjustments?








{{-- Featured Products --}}
        <section class="py-20 border-b border-zinc-800">
            <div class="container mx-auto px-4 max-w-7xl">
                <div class="mb-12 text-center">
                    <h2 class="text-3xl font-bold tracking-tight md:text-4xl">Featured Products</h2>
                    <p class="mt-4 text-zinc-400">Discover our most popular code solutions</p>
                </div>

                <div x-data="{ tab: 'all' }">
                    <div class="flex justify-center mb-8">
                        <div class="inline-flex rounded-md bg-zinc-900 p-1">
                            <button @click="tab = 'all'"
                                :class="{ 'bg-white text-zinc-900': tab === 'all', 'text-zinc-400': tab !== 'all' }"
                                class="px-3 py-1.5 text-sm font-medium rounded-md">All</button>
                            <button @click="tab = 'scripts'"
                                :class="{ 'bg-white text-zinc-900': tab === 'scripts', 'text-zinc-400': tab !== 'scripts' }"
                                class="px-3 py-1.5 text-sm font-medium rounded-md">Scripts</button>
                            <button @click="tab = 'templates'"
                                :class="{ 'bg-white text-zinc-900': tab === 'templates', 'text-zinc-400': tab !== 'templates' }"
                                class="px-3 py-1.5 text-sm font-medium rounded-md">Templates</button>
                            <button @click="tab = 'plugins'"
                                :class="{ 'bg-white text-zinc-900': tab === 'plugins', 'text-zinc-400': tab !== 'plugins' }"
                                class="px-3 py-1.5 text-sm font-medium rounded-md">Plugins</button>
                        </div>
                    </div>

