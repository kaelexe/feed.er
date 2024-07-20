<template>
    <nav class="navbar">
        
            <div class="navbar-brand">
                <a href="/" class="navbar-item">
                    <h1 class="logo">feed.er</h1>
                </a>
                <div class="navbar-brand-end">
                    <Button @click="toggleColorMode" variant="ghost">
                        <span v-if="mode === 'light'"><Moon /></span>
                        <span v-else><Sun /></span>
                    </Button>
                </div>
            </div>
            <div id="navbarMenu" class="navbar-menu">
                <div class="navbar-end"></div>
            </div>
    </nav>
</template>

<script setup lang="ts">

import { Button } from './ui/button';
import { useColorMode } from '@vueuse/core';
import { Sun, Moon } from 'lucide-vue-next';

const mode = useColorMode();

const toggleColorMode = () => {
  if (mode.value === 'light') {
    mode.value = 'dark';
  } else {
    mode.value = 'light';
  }
};

</script>

<style scoped>
    .navbar {
        background-color: #4E596F;
        box-shadow: 0 2px 4px rgba(0, 0, 0, 0.1);
        padding: 1rem 1rem;
        width: 100%;
    }

    .logo {
        color: white;
        font-size: 1.5rem;
        font-weight: bold;
    }

    .navbar-brand {
        display: flex;
        justify-content: space-between;
        align-items: center;
    }

    .navbar-item {
        color: white;
        text-decoration: none;
    }

    .navbar-end, .navbar-brand-end {
        display: flex;
        justify-content: flex-end;
    }
</style>