<script setup>
import { Head, Link } from "@inertiajs/vue3";

defineProps({
    canLogin: {
        type: Boolean,
    },
    canRegister: {
        type: Boolean,
    },
    laravelVersion: {
        type: String,
        required: true,
    },
    phpVersion: {
        type: String,
        required: true,
    },
});
</script>

<template>
    <Head title="Welcome" />

    <div
        class="relative sm:flex sm:justify-center sm:items-center min-h-screen bg-dots-darker bg-center bg-gray-100 dark:bg-dots-lighter dark:bg-gray-900 selection:bg-red-500 selection:text-white"
    >
        <div
            v-if="canLogin"
            class="sm:fixed sm:top-0 sm:right-0 p-6 text-right"
        >
            <Link
                v-if="$page.props.auth.user"
                :href="route('dashboard')"
                class="font-semibold text-gray-600 hover:text-gray-900 dark:text-gray-400 text-xl dark:hover:text-white focus:outline focus:outline-2 focus:rounded-sm focus:outline-red-500"
                >Dashboard</Link
            >

            <template v-else>
                <Link
                    :href="route('login')"
                    class="font-semibold text-gray-600 hover:text-gray-900 dark:text-gray-400 text-xl dark:hover:text-white focus:outline focus:outline-2 focus:rounded-sm focus:outline-red-500"
                    >Log in</Link
                >

                <Link
                    v-if="canRegister"
                    :href="route('register')"
                    class="ml-4 font-semibold text-gray-600 hover:text-gray-900 dark:text-gray-400 text-xl dark:hover:text-white focus:outline focus:outline-2 focus:rounded-sm focus:outline-red-500"
                    >Register</Link
                >
            </template>
        </div>

        <div class="max-w-7xl mx-auto p-6 lg:p-8">
            <div class="flex justify-center">
                <svg
                    viewBox="0 0 62 65"
                    xmlns="http://www.w3.org/2000/svg"
                    fill="none"
                    class="h-16 w-auto bg-gray-100 dark:bg-gray-900"
                >
                    <g fill="#FF2D20">
                        <path
                            d="M47.273 14.2h-8.916V.727A.727.727 0 0 0 37.63 0H.727A.726.726 0 0 0 0 .727v39.881a.726.726 0 0 0 .453.674.752.752 0 0 0 .274.055.729.729 0 0 0 .521-.219l7.961-8.148h7.527v7.17a.729.729 0 0 0 .727.729H40l6.756 6.914a.725.725 0 0 0 .52.219.744.744 0 0 0 .274-.055.729.729 0 0 0 .45-.674V14.925a.728.728 0 0 0-.727-.725zm-33.22 17.315V24.07a.728.728 0 0 0-1.455 0v7.445H9.453v-8.242a3.876 3.876 0 0 1 3.872-3.873h2.943a.728.728 0 0 0 0-1.456h-2.943A5.333 5.333 0 0 0 8 23.272v8.852l-6.545 6.7V1.454H36.9v30.061h-6.543v-8.242a5.332 5.332 0 0 0-5.326-5.326h-2.943a.728.728 0 0 0 0 1.456h2.943a3.876 3.876 0 0 1 3.869 3.871v8.242h-3.142v-7.445a.727.727 0 0 0-1.454 0v7.445H14.053zm32.492 13.972-5.723-5.855a.721.721 0 0 0-.52-.219H18.19V32.97h19.439a.728.728 0 0 0 .727-.727V15.651h8.188v29.836z"
                        />
                        <path
                            d="M23.933 11.015a4.755 4.755 0 1 0-4.754 4.756 4.759 4.759 0 0 0 4.754-4.756zm-8.055 0a3.3 3.3 0 1 1 3.3 3.3 3.3 3.3 0 0 1-3.3-3.3zM19.178 17.946a.728.728 0 0 0-.728.729v9.689a.728.728 0 0 0 1.455 0v-9.689a.727.727 0 0 0-.727-.729z"
                        />
                    </g>
                </svg>
            </div>

            <div class="mt-16">
                <div class="grid grid-cols-1 md:grid-cols-2 gap-6 lg:gap-8">
                    <a
                        href="#"
                        class="scale-100 p-6 bg-white dark:bg-gray-800/50 dark:bg-gradient-to-bl from-gray-700/50 via-transparent dark:ring-1 dark:ring-inset dark:ring-white/5 rounded-lg shadow-2xl shadow-gray-500/20 dark:shadow-none flex motion-safe:hover:scale-[1.01] transition-all duration-250 focus:outline focus:outline-2 focus:outline-red-500"
                    >
                        <div>
                            <div
                                class="h-16 w-16 bg-red-50 dark:bg-red-800/20 flex items-center justify-center rounded-full"
                            >
                                <svg
                                    xmlns="http://www.w3.org/2000/svg"
                                    fill="none"
                                    viewBox="0 0 24 24"
                                    stroke-width="1.5"
                                    stroke="currentColor"
                                    class="w-6 h-6 stroke-red-500"
                                >
                                    <path
                                        stroke-linecap="round"
                                        stroke-linejoin="round"
                                        d="M8.625 9.75a.375.375 0 11-.75 0 .375.375 0 01.75 0zm0 0H8.25m4.125 0a.375.375 0 11-.75 0 .375.375 0 01.75 0zm0 0H12m4.125 0a.375.375 0 11-.75 0 .375.375 0 01.75 0zm0 0h-.375m-13.5 3.01c0 1.6 1.123 2.994 2.707 3.227 1.087.16 2.185.283 3.293.369V21l4.184-4.183a1.14 1.14 0 01.778-.332 48.294 48.294 0 005.83-.498c1.585-.233 2.708-1.626 2.708-3.228V6.741c0-1.602-1.123-2.995-2.707-3.228A48.394 48.394 0 0012 3c-2.392 0-4.744.175-7.043.513C3.373 3.746 2.25 5.14 2.25 6.741v6.018z"
                                    />
                                </svg>
                            </div>

                            <h2
                                class="mt-6 text-xl font-semibold text-gray-900 dark:text-white"
                            >
                                Conversations
                            </h2>

                            <p
                                class="mt-4 text-gray-500 dark:text-gray-400 text-sm leading-relaxed"
                            >
                                Engage in AI-driven dialogues, exploring diverse
                                topics and experiencing natural, contextually
                                relevant interactions. ConvoGenius leverages the
                                powerful GPT-3.5 API to simulate meaningful
                                conversations, catering to users' queries and
                                discussions.
                            </p>
                        </div>
                    </a>

                    <a
                        href="#"
                        class="scale-100 p-6 bg-white dark:bg-gray-800/50 dark:bg-gradient-to-bl from-gray-700/50 via-transparent dark:ring-1 dark:ring-inset dark:ring-white/5 rounded-lg shadow-2xl shadow-gray-500/20 dark:shadow-none flex motion-safe:hover:scale-[1.01] transition-all duration-250 focus:outline focus:outline-2 focus:outline-red-500"
                    >
                        <div>
                            <div
                                class="h-16 w-16 bg-red-50 dark:bg-red-800/20 flex items-center justify-center rounded-full"
                            >
                                <svg
                                    xmlns="http://www.w3.org/2000/svg"
                                    fill="none"
                                    viewBox="0 0 24 24"
                                    stroke-width="1.5"
                                    stroke="currentColor"
                                    class="w-6 h-6 stroke-red-500"
                                >
                                    <path
                                        stroke-linecap="round"
                                        stroke-linejoin="round"
                                        d="M17.982 18.725A7.488 7.488 0 0012 15.75a7.488 7.488 0 00-5.982 2.975m11.963 0a9 9 0 10-11.963 0m11.963 0A8.966 8.966 0 0112 21a8.966 8.966 0 01-5.982-2.275M15 9.75a3 3 0 11-6 0 3 3 0 016 0z"
                                    />
                                </svg>
                            </div>

                            <h2
                                class="mt-6 text-xl font-semibold text-gray-900 dark:text-white"
                            >
                                User Accounts
                            </h2>

                            <p
                                class="mt-4 text-gray-500 dark:text-gray-400 text-sm leading-relaxed"
                            >
                                Access a personalized experience through
                                individual user accounts. Users can create,
                                manage, and customize their interactions,
                                ensuring a tailored environment for conversing
                                with ConvoGenius and retaining conversation
                                histories(Login/Register to start now).
                            </p>
                        </div>
                    </a>

                    <a
                        href=""
                        class="scale-100 p-6 bg-white dark:bg-gray-800/50 dark:bg-gradient-to-bl from-gray-700/50 via-transparent dark:ring-1 dark:ring-inset dark:ring-white/5 rounded-lg shadow-2xl shadow-gray-500/20 dark:shadow-none flex motion-safe:hover:scale-[1.01] transition-all duration-250 focus:outline focus:outline-2 focus:outline-red-500"
                    >
                        <div>
                            <div
                                class="h-16 w-16 bg-red-50 dark:bg-red-800/20 flex items-center justify-center rounded-full"
                            >
                                <svg
                                    xmlns="http://www.w3.org/2000/svg"
                                    fill="none"
                                    viewBox="0 0 24 24"
                                    stroke-width="1.5"
                                    stroke="currentColor"
                                    class="w-6 h-6 stroke-red-500"
                                >
                                    <path
                                        stroke-linecap="round"
                                        stroke-linejoin="round"
                                        d="M19.5 14.25v-2.625a3.375 3.375 0 00-3.375-3.375h-1.5A1.125 1.125 0 0113.5 7.125v-1.5a3.375 3.375 0 00-3.375-3.375H8.25M9 16.5v.75m3-3v3M15 12v5.25m-4.5-15H5.625c-.621 0-1.125.504-1.125 1.125v17.25c0 .621.504 1.125 1.125 1.125h12.75c.621 0 1.125-.504 1.125-1.125V11.25a9 9 0 00-9-9z"
                                    />
                                </svg>
                            </div>

                            <h2
                                class="mt-6 text-xl font-semibold text-gray-900 dark:text-white"
                            >
                                History
                            </h2>

                            <p
                                class="mt-4 text-gray-500 dark:text-gray-400 text-sm leading-relaxed"
                            >
                                Effortlessly manage and navigate conversation
                                records within ConvoGenius. Users have the
                                capability to review, search, and delete chat
                                histories, offering control and organization
                                over past interactions for a streamlined user
                                experience.
                            </p>
                        </div>
                    </a>

                    <div
                        class="scale-100 p-6 bg-white dark:bg-gray-800/50 dark:bg-gradient-to-bl from-gray-700/50 via-transparent dark:ring-1 dark:ring-inset dark:ring-white/5 rounded-lg shadow-2xl shadow-gray-500/20 dark:shadow-none flex motion-safe:hover:scale-[1.01] transition-all duration-250 focus:outline focus:outline-2 focus:outline-red-500"
                    >
                        <div>
                            <div
                                class="h-16 w-16 bg-red-50 dark:bg-red-800/20 flex items-center justify-center rounded-full"
                            >
                                <svg
                                    xmlns="http://www.w3.org/2000/svg"
                                    fill="none"
                                    viewBox="0 0 24 24"
                                    stroke-width="1.5"
                                    stroke="currentColor"
                                    class="w-6 h-6 stroke-red-500"
                                >
                                    <path
                                        stroke-linecap="round"
                                        stroke-linejoin="round"
                                        d="M9 12.75L11.25 15 15 9.75m-3-7.036A11.959 11.959 0 013.598 6 11.99 11.99 0 003 9.749c0 5.592 3.824 10.29 9 11.623 5.176-1.332 9-6.03 9-11.622 0-1.31-.21-2.571-.598-3.751h-.152c-3.196 0-6.1-1.248-8.25-3.285z"
                                    />
                                </svg>
                            </div>

                            <h2
                                class="mt-6 text-xl font-semibold text-gray-900 dark:text-white"
                            >
                                Security
                            </h2>

                            <p
                                class="mt-4 text-gray-500 dark:text-gray-400 text-sm leading-relaxed"
                            >
                                Prioritize user data privacy and security within
                                ConvoGenius. The platform implements robust
                                measures to safeguard user information, ensuring
                                encryption, secure storage, and ethical handling
                                of conversational data, bolstering trust and
                                confidentiality.
                            </p>
                        </div>
                    </div>
                </div>
            </div>
        </div>
    </div>
</template>

<style>
.bg-dots-darker {
    background-image: url("data:image/svg+xml,%3Csvg width='30' height='30' viewBox='0 0 30 30' fill='none' xmlns='http://www.w3.org/2000/svg'%3E%3Cpath d='M1.22676 0C1.91374 0 2.45351 0.539773 2.45351 1.22676C2.45351 1.91374 1.91374 2.45351 1.22676 2.45351C0.539773 2.45351 0 1.91374 0 1.22676C0 0.539773 0.539773 0 1.22676 0Z' fill='rgba(0,0,0,0.07)'/%3E%3C/svg%3E");
}
@media (prefers-color-scheme: dark) {
    .dark\:bg-dots-lighter {
        background-image: url("data:image/svg+xml,%3Csvg width='30' height='30' viewBox='0 0 30 30' fill='none' xmlns='http://www.w3.org/2000/svg'%3E%3Cpath d='M1.22676 0C1.91374 0 2.45351 0.539773 2.45351 1.22676C2.45351 1.91374 1.91374 2.45351 1.22676 2.45351C0.539773 2.45351 0 1.91374 0 1.22676C0 0.539773 0.539773 0 1.22676 0Z' fill='rgba(255,255,255,0.07)'/%3E%3C/svg%3E");
    }
}
</style>
