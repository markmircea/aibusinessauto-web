<script setup>
import { ref } from 'vue';
import { Link } from '@inertiajs/vue3';
import Dropdown from '@/Components/Dropdown.vue';
import DropdownLink from '@/Components/DropdownLink.vue';

const solutions = [
    { name: 'Document Processing', route: 'solutions.document-processing' },
    { name: 'Customer Service', route: 'solutions.customer-service' },
    { name: 'Financial Operations', route: 'solutions.financial-operations' },
    { name: 'HR & Recruitment', route: 'solutions.hr-recruitment' },
    { name: 'Sales & Marketing', route: 'solutions.sales-marketing' },
    { name: 'Supply Chain', route: 'solutions.supply-chain' }
];
</script>

<template>
    <Dropdown align="left" width="48">
        <template #trigger>
            <button class="inline-flex items-center px-3 py-2 text-sm leading-4 font-medium text-gray-500 dark:text-gray-400 hover:text-gray-700 dark:hover:text-gray-300 focus:outline-none transition ease-in-out duration-150">
                Solutions
                <svg class="ms-2 -me-0.5 h-4 w-4" xmlns="http://www.w3.org/2000/svg" fill="none" viewBox="0 0 24 24" stroke-width="1.5" stroke="currentColor">
                    <path stroke-linecap="round" stroke-linejoin="round" d="M19.5 8.25l-7.5 7.5-7.5-7.5" />
                </svg>
            </button>
        </template>

        <template #content>
            <div class="w-full p-2">
                <div v-for="solution in solutions" :key="solution.route" class="w-full">
                    <Link :href="route(solution.route)" class="block w-full px-4 py-2 text-sm leading-5 text-gray-700 dark:text-gray-300 hover:bg-gray-100 dark:hover:bg-gray-800 focus:outline-none focus:bg-gray-100 dark:focus:bg-gray-800 transition duration-150 ease-in-out">
                        {{ solution.name }}
                    </Link>
                </div>
            </div>
        </template>
    </Dropdown>
</template>
