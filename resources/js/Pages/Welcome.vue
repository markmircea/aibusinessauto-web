<script setup>
import { Head, Link } from '@inertiajs/vue3';
import HeroSection from '@/Components/HeroSection.vue';
import SolutionsSection from '@/Components/SolutionsSection.vue';

defineProps({
    canLogin: Boolean,
    canRegister: Boolean,
});
</script>

<template>
    <Head>
        <title>AI Business Automation Solutions</title>
        <meta name="description" content="Transform your business operations with AI automation. Streamline processes, reduce costs, and boost efficiency with our cutting-edge solutions." />
    </Head>

    <div class="min-h-screen bg-white dark:bg-gray-900">
        <!-- Navigation -->
        <nav class="fixed top-0 w-full bg-white/80 dark:bg-gray-900/80 backdrop-blur-md z-50 border-b border-gray-200 dark:border-gray-800">
            <div class="max-w-7xl mx-auto px-4 sm:px-6 lg:px-8">
                <div class="flex justify-between h-16">
                    <div class="flex items-center">
                        <!-- Logo -->
                        <div class="text-2xl font-bold text-blue-600 dark:text-blue-400">
                            AutomateAI
                        </div>
                    </div>

                    <!-- Navigation Links -->
                    <div class="hidden sm:flex sm:items-center sm:space-x-8">
                        <a href="#solutions" class="text-gray-600 hover:text-gray-900 dark:text-gray-300 dark:hover:text-white px-3 py-2 text-sm font-medium">Solutions</a>
                        <a href="#benefits" class="text-gray-600 hover:text-gray-900 dark:text-gray-300 dark:hover:text-white px-3 py-2 text-sm font-medium">Benefits</a>
                        
                        <div v-if="canLogin" class="flex items-center space-x-4">
                            <Link 
                                v-if="$page.props.auth.user" 
                                :href="route('dashboard')" 
                                class="text-gray-600 hover:text-gray-900 dark:text-gray-300 dark:hover:text-white px-3 py-2 text-sm font-medium"
                            >
                                Dashboard
                            </Link>

                            <template v-else>
                                <Link 
                                    :href="route('login')" 
                                    class="text-gray-600 hover:text-gray-900 dark:text-gray-300 dark:hover:text-white px-3 py-2 text-sm font-medium"
                                >
                                    Log in
                                </Link>

                                <Link 
                                    v-if="canRegister" 
                                    :href="route('register')" 
                                    class="inline-flex items-center px-4 py-2 border border-transparent text-sm font-medium rounded-md text-white bg-blue-600 hover:bg-blue-700"
                                >
                                    Get Started
                                </Link>
                            </template>
                        </div>
                    </div>
                </div>
            </div>
        </nav>

        <!-- Main Content -->
        <main>
            <!-- Hero Section -->
            <HeroSection />

            <!-- Solutions Section -->
            <SolutionsSection />

            <!-- Benefits Section -->
            <section id="benefits" class="py-20 bg-white dark:bg-gray-800">
                <div class="max-w-7xl mx-auto px-4 sm:px-6 lg:px-8">
                    <div class="text-center mb-16">
                        <h2 class="text-3xl sm:text-4xl font-bold text-gray-900 dark:text-white mb-4">
                            Why Choose Our AI Solutions?
                        </h2>
                        <p class="max-w-2xl mx-auto text-lg text-gray-600 dark:text-gray-300">
                            Experience the power of AI-driven automation with proven results and enterprise-grade security.
                        </p>
                    </div>

                    <div class="grid grid-cols-1 md:grid-cols-3 gap-8">
                        <div class="p-6 bg-gray-50 dark:bg-gray-700 rounded-lg">
                            <div class="w-12 h-12 bg-blue-100 dark:bg-blue-800 rounded-lg flex items-center justify-center mb-4">
                                <svg class="w-6 h-6 text-blue-600 dark:text-blue-300" fill="none" stroke="currentColor" viewBox="0 0 24 24">
                                    <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M13 10V3L4 14h7v7l9-11h-7z" />
                                </svg>
                            </div>
                            <h3 class="text-xl font-semibold text-gray-900 dark:text-white mb-2">Fast Implementation</h3>
                            <p class="text-gray-600 dark:text-gray-300">Quick deployment with minimal disruption to your existing workflows.</p>
                        </div>

                        <div class="p-6 bg-gray-50 dark:bg-gray-700 rounded-lg">
                            <div class="w-12 h-12 bg-blue-100 dark:bg-blue-800 rounded-lg flex items-center justify-center mb-4">
                                <svg class="w-6 h-6 text-blue-600 dark:text-blue-300" fill="none" stroke="currentColor" viewBox="0 0 24 24">
                                    <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M9 12l2 2 4-4m5.618-4.016A11.955 11.955 0 0112 2.944a11.955 11.955 0 01-8.618 3.04A12.02 12.02 0 003 9c0 5.591 3.824 10.29 9 11.622 5.176-1.332 9-6.03 9-11.622 0-1.042-.133-2.052-.382-3.016z" />
                                </svg>
                            </div>
                            <h3 class="text-xl font-semibold text-gray-900 dark:text-white mb-2">Enterprise Security</h3>
                            <p class="text-gray-600 dark:text-gray-300">Bank-grade security with data encryption and compliance standards.</p>
                        </div>

                        <div class="p-6 bg-gray-50 dark:bg-gray-700 rounded-lg">
                            <div class="w-12 h-12 bg-blue-100 dark:bg-blue-800 rounded-lg flex items-center justify-center mb-4">
                                <svg class="w-6 h-6 text-blue-600 dark:text-blue-300" fill="none" stroke="currentColor" viewBox="0 0 24 24">
                                    <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M9 19v-6a2 2 0 00-2-2H5a2 2 0 00-2 2v6a2 2 0 002 2h2a2 2 0 002-2zm0 0V9a2 2 0 012-2h2a2 2 0 012 2v10m-6 0a2 2 0 002 2h2a2 2 0 002-2m0 0V5a2 2 0 012-2h2a2 2 0 012 2v14a2 2 0 01-2 2h-2a2 2 0 01-2-2z" />
                                </svg>
                            </div>
                            <h3 class="text-xl font-semibold text-gray-900 dark:text-white mb-2">Measurable ROI</h3>
                            <p class="text-gray-600 dark:text-gray-300">Clear metrics and reporting to track your automation success.</p>
                        </div>
                    </div>
                </div>
            </section>

            <!-- Footer -->
            <footer class="bg-gray-50 dark:bg-gray-900 border-t border-gray-200 dark:border-gray-800">
                <div class="max-w-7xl mx-auto py-12 px-4 sm:px-6 lg:px-8">
                    <div class="text-center text-gray-500 dark:text-gray-400">
                        <p>&copy; 2025 AutomateAI. All rights reserved.</p>
                    </div>
                </div>
            </footer>
        </main>
    </div>
</template>

<style>
html {
    scroll-behavior: smooth;
}
</style>
