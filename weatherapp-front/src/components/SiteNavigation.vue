<template>
    <header class="sticky top-0 bg-weather-primary shadow-lg">
        <nav class="container flex flex-col sm:flex-row items-center gap-4 text-white py-6">
            <RouterLink :to="{ name: 'home' }">
                <div class="flex items-center gap-3 flex-1 p-4">
                    <i class="fa fa-solid fa-sun text-2xl text-white"></i>
                    <text class="text-white text-2xl">Hugo's Weather App</text>
                </div>
            </RouterLink>

            <div class="flex flex-1 gap-3 justify-end">
                <i class="fa fa-solid fa-circle-info text-white text-xl
                    hover:text-weather-secondary duration-150 cursor-pointer" @click="toggleModal"></i>
                <i class="fa fa-solid fa-plus text-white text-xl
                    hover:text-weather-secondary duration-150 cursor-pointer"></i>
            </div>

            <BaseModal :modalActive="modalActive" @close-modal="toggleModal">
                <div class="text-black">
                    <h1 class="text-2xl mb-1">About:</h1>
                    <p class="mb-4">
                        The Local Weather allows you to track the current and
                        future weather of cities of your choosing.
                    </p>
                    <h2 class="text-2xl">How it works:</h2>
                    <ol class="list-decimal list-inside mb-4">
                        <li>
                            Search for your city by entering the name into the
                            search bar.
                        </li>
                        <li>
                            Select a city within the results, this will take
                            you to the current weather for your selection.
                        </li>
                        <li>
                            Track the city by clicking on the "+" icon in the
                            top right. This will save the city to view at a
                            later time on the home page.
                        </li>
                    </ol>

                    <h2 class="text-2xl">Removing a city</h2>
                    <p>
                        If you no longer wish to track a city, simply select
                        the city within the home page. At the bottom of the
                        page, there will be am option to delete the city.
                    </p>

                    <h2 class="text-2xl">More info:</h2>
                    <p>
                        This app was created by Hugo Bonnell, based on the tutorial of
                        Net Ninja. (Please see https://github.com/johnkomarnicki/net_ninja_vue_3_weather_app).
                        The objective being learning how to use Vue and Tailwind !
                    </p>
                </div>
            </BaseModal>
        </nav>
    </header>
</template>

<script setup>
import { RouterLink } from 'vue-router';
import { ref } from 'vue';
import BaseModal from './BaseModal.vue';

const modalActive = ref(null);
const toggleModal = () => {
    modalActive.value = !modalActive.value;
};
</script>
