<template>
    <div>
        <app-header />
        <!-- <app-footer/> -->
        <div class="container">
            <button @click="activeComp = Mike">Mike</button>
            <button @click="activeComp = Steve">Steve</button>
            <!-- <Mike v-if="activeComp === Mike" /> -->
            <!-- <Steve v-if="activeComp === Steve" /> -->
            <!-- <component :is="activeComp"></component> -->
            <keep-alive include="mike,steve">
                <component :is="activeComp"></component>
            </keep-alive>
        </div>
    </div>
</template>

<script setup>
    import { ref, shallowRef, reactive, provide } from 'vue';
    import Mike from '@/components/Players/mike.vue';
    import Steve from '@/components/Players/steve.vue';

    const activeComp = shallowRef(Mike);

</script>

<style>
    body {
        padding: 0;
        margin: 0;
        font-family: 'Roboto', sans-serif;
    }
    .container {
        min-height: 84vh;
        box-sizing: border-box;
        padding: 20px;
    }

</style> 