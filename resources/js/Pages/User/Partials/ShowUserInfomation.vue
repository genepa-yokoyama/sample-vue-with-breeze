<script setup>
import InputError from '@/Components/InputError.vue';
import InputLabel from '@/Components/InputLabel.vue';
import PrimaryButton from '@/Components/PrimaryButton.vue';
import SecondaryButton from '@/Components/SecondaryButton.vue';
import TextInput from '@/Components/TextInput.vue';
import { Link, useForm, usePage } from '@inertiajs/vue3';

defineProps({
});

const user = usePage().props.user;
</script>

<template>
    <section>
        <header>
            <h2 class="text-lg font-medium text-gray-900 dark:text-gray-100">User Information</h2>

            <p class="mt-1 text-sm text-gray-600 dark:text-gray-400">
                show user information
            </p>
        </header>

            <div class="mt-6">
                <InputLabel for="name" value="Name" />

                <p class="mt-2 text-sm text-gray-800 dark:text-gray-200">
                    {{ user.name }}
                </p>
            </div>

            <div class="mt-6">
                <InputLabel for="email" value="Email" />

                <p class="mt-2 text-sm text-gray-800 dark:text-gray-200">
                    {{ user.email }}
                </p>
            </div>

            <div class="flex items-center gap-4 mt-6">
                <SecondaryButton>
                    <a :href="route('user.edit', user.id)">Edit User</a>
                </SecondaryButton>
            </div>
    </section>
</template>
