<script setup>
import { Head, Link } from '@inertiajs/vue3';
import Content from './Components/Assets/Content.vue';
import DefaultButton from './Components/Assets/DefaultButton.vue';

defineProps({
    canLogin: {
        type: Boolean,
    },
    canRegister: {
        type: Boolean,
    },
});
</script>

<template>
    <Head title="Bem Vindo" />

    <header class="flex flex-wrap w-full">
        <section class="flex w-full p-4 text-white bg-gray-600">
            <Content class="items-center justify-between">
                <div class="font-bold text-white font-xl">
                    Meu App
                </div>

                <div v-if="canLogin" class="font-bold text-white font-xl">


                    <Link v-if="$page.props.auth.user" :href="route('dashboard')" class="">
                    Dashboard</Link>

                    <template v-else>
                       <DefaultButton class="mr-2"> <Link :href="route('login')" class="">
                        Log in</Link></DefaultButton>

                      <DefaultButton>
                        <Link v-if="canRegister" :href="route('register')" class="">
                        Register</Link>
                      </DefaultButton>

                    </template>
                </div>


            </Content>

        </section>


    </header>
</template>

<style scoped>


</style>
