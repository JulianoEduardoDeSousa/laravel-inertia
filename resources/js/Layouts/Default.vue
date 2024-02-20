<script setup>
import { Head, Link } from '@inertiajs/vue3';
import Content from '../Pages/Components/Assets/Content.vue';
import DefaultButton from '../Pages/Components/Assets/DefaultButton.vue';
import NavMenu from '../Pages/Components/Assets/Nav/NavMenu.vue';
import NavItem from '../Pages/Components/Assets/Nav/NavItem.vue';

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
        <section class="flex w-full p-4 text-white bg-[#181818]">
            <Content class="items-center justify-between">
                <div class="logo">
                    Meu App
                </div>

                <div v-if="canLogin" class="font-bold text-white font-xl">


                    <Link v-if="$page.props.auth.user" :href="route('dashboard')" class="">
                    Dashboard</Link>

                    <template v-else>
                        <DefaultButton class="mr-2">
                            <Link :href="route('login')" class="">
                            Log in</Link>
                        </DefaultButton>

                        <DefaultButton>
                            <Link v-if="canRegister" :href="route('register')" class="">
                            Register</Link>
                        </DefaultButton>

                    </template>
                </div>


            </Content>

        </section>
        <NavMenu>
            <NavItem>Home</NavItem>
            <NavItem>Sobre</NavItem>
            <NavItem>Notícias</NavItem>
            <NavItem>Contato</NavItem>
        </NavMenu>






    </header>
    <slot />
</template>
<style scoped>
.logo {
    @apply text-white text-xl font-bold;
    background-image: linear-gradient(to right, #42b883, rgb(14 116 144));
    background-clip: text;
    -webkit-text-fill-color: transparent;
}
</style>

