<template>
  <nav class="navbar">
    <div class="navbar-brand">
      <a href="/" class="navbar-item">
        <h1 class="logo">feed.er</h1>
      </a>
      <div class="navbar-brand-end">
        <DropdownMenu>
          <DropdownMenuTrigger>
            <ChevronDown class="text-white" />
          </DropdownMenuTrigger>
          <DropdownMenuContent>
            <DropdownMenuSub>
              <DropdownMenuSubTrigger>
                <DropdownMenuLabel>Theme</DropdownMenuLabel>
                <DropdownMenuPortal>
                  <DropdownMenuSubContent>
                    <DropdownMenuItem
                      @click="mode = 'light'"
                      class="flex gap-3"
                    >
                      <Sun class="w-5 h-5" />Light
                    </DropdownMenuItem>
                    <DropdownMenuItem @click="mode = 'dark'" class="flex gap-3">
                      <Moon class="w-5 h-5" /> Dark
                    </DropdownMenuItem>
                    <DropdownMenuItem @click="mode = 'auto'">
                      System
                    </DropdownMenuItem>
                  </DropdownMenuSubContent>
                </DropdownMenuPortal>
              </DropdownMenuSubTrigger>
            </DropdownMenuSub>
            <DropdownMenuSeparator />
            <DropdownMenuItem>
              <DropdownMenuLabel class="text-destructive" @click="onLogout"
                >Logout</DropdownMenuLabel
              >
            </DropdownMenuItem>
          </DropdownMenuContent>
        </DropdownMenu>
      </div>
    </div>
    <div id="navbarMenu" class="navbar-menu">
      <div class="navbar-end"></div>
    </div>
  </nav>
</template>

<script setup lang="ts">
import { useColorMode } from "@vueuse/core";
import { Sun, Moon } from "lucide-vue-next";
import { ChevronDown } from "lucide-vue-next";
import {
  DropdownMenu,
  DropdownMenuContent,
  DropdownMenuItem,
  DropdownMenuLabel,
  DropdownMenuSeparator,
  DropdownMenuTrigger,
  DropdownMenuSub,
  DropdownMenuSubTrigger,
  DropdownMenuSubContent,
  DropdownMenuPortal,
} from "./ui/dropdown-menu";

const mode = useColorMode();

const onLogout = () => {
  console.log("Logging out...");
};

</script>

<style scoped>
.navbar {
  background-color: #4e596f;
  box-shadow: 0 2px 4px rgba(0, 0, 0, 0.1);
  padding: 1rem 1rem;
  width: 100%;
}

.logo {
  color: white;
  font-size: 1.5rem;
  font-weight: bold;
  font-style: italic;
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

.navbar-end,
.navbar-brand-end {
  display: flex;
  justify-content: flex-end;
}
</style>
