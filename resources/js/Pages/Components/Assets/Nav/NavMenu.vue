<script setup>
import Content from '../../Assets/Content.vue';

</script>
<template>
    <section class="flex w-full p-4 text-white bg-gray-600 border-solid border-t-[1px] border-t-black">
        <Content class="items-center ">
            <ul class="flex w-full">
               <slot/>
            </ul>
        </Content>
    </section>
</template>
