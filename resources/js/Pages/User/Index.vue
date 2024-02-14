<script setup>
import AuthenticatedLayout from '@/Layouts/AuthenticatedLayout.vue';
import PrimaryButton from '@/Components/PrimaryButton.vue';
import { Head } from '@inertiajs/vue3';

defineProps({
    users: {
        type: Array,
        required: true,
    },
});

</script>

<template>
    <Head title="User" />

    <AuthenticatedLayout>
        <template #header>
            <h2 class="font-semibold text-xl text-gray-800 dark:text-gray-200 leading-tight">Users</h2>
        </template>

        <div class="py-12">
            <div class="max-w-7xl mx-auto sm:px-6 lg:px-8 space-y-6">
                <PrimaryButton>
                    <a :href="route('user.create')">Create User</a>
                </PrimaryButton>

                <div class="p-4 sm:p-8 bg-white dark:bg-gray-800 shadow sm:rounded-lg">
                    <table class="min-w-full">
                        <thead>
                            <tr>
                                <th
                                    class="px-6 py-3 border-b-2 border-gray-300 dark:border-gray-700 bg-gray-50 dark:bg-gray-700 text-left text-xs font-semibold text-gray-600 dark:text-gray-400 uppercase tracking-wider">
                                    Name
                                </th>
                                <th
                                    class="px-6 py-3 border-b-2 border-gray-300 dark:border-gray-700 bg-gray-50 dark:bg-gray-700 text-left text-xs font-semibold text-gray-600 dark:text-gray-400 uppercase tracking-wider">
                                    Email
                                </th>
                                <th
                                    class="px-6 py-3 border-b-2 border-gray-300 dark:border-gray-700 bg-gray-50 dark:bg-gray-700 text-left text-xs font-semibold text-gray-600 dark:text-gray-400 uppercase tracking-wider">
                                    Role
                                </th>
                            </tr>
                        </thead>
                        <tbody>
                            <tr v-for="user in users" :key="user.id">
                                <td class="px-6 py-4 border-b-2 whitespace-nowrap">
                                    <a :href="route('user.show', user.id)"
                                        class="text-blue-500 hover:underline hover:text-blue-700">{{ user.name }}</a>
                                </td>
                                <td class="px-6 py-4 border-b-2 whitespace-nowrap">
                                    <span class="text-gray-900 dark:text-gray-200">{{ user.email }}</span>
                                </td>
                                <td class="px-6 py-4 border-b-2 whitespace-nowrap">
                                    <span class="text-gray-900 dark:text-gray-200">{{ user.role }}</span>
                                </td>
                            </tr>
                        </tbody>
                    </table>
                </div>
            </div>
        </div>

</AuthenticatedLayout></template>
