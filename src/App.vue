<script setup lang="ts">
import { ref } from 'vue';
import AboutMe from './components/AboutMe.vue'
import Experience from './components/Experience.vue'
import Education from './components/Education.vue'

const routePath = ref("about");

function setPath(path: string) {
	routePath.value = path;
}

function comparePath(path: string) {
	return routePath.value === path
}
</script>

<template>
	<div class="flex h-screen">
		<div class="hidden lg:flex flex-col w-80 bg-violet-500 items-center justify-center">
			<div id="circle" class="h-40 w-40 rounded-full border-8 border-violet-400 overflow-hidden mb-10">
				<img src="./assets/profile.png" alt="">
			</div>
			<ul class="flex flex-col text-white font-bold text-violet-300 gap-4 items-center text-2xl">
				<a @click="setPath('about')" class="cursor-pointer hover:text-violet-100"
					:class="{ 'text-white': comparePath('about') }" href="#about">ABOUT</a>
				<a @click="setPath('experience')" class="cursor-pointer hover:text-violet-100"
					:class="{ 'text-white': comparePath('experience') }" href="#experience">EXPERIENCE</a>
				<a @click="setPath('education')" class="cursor-pointer hover:text-violet-100"
					:class="{ 'text-white': comparePath('education') }" href="#education">EDUCATION</a>
				<a @click="setPath('skills')" class="cursor-pointer hover:text-violet-100"
					:class="{ 'text-white': comparePath('skills') }" href="#skills">SKILLS</a>
				<a @click="setPath('interest')" class="cursor-pointer hover:text-violet-100"
					:class="{ 'text-white': comparePath('interest') }" href="#interest">INTEREST</a>
				<a @click="setPath('portfolio')" class="cursor-pointer hover:text-violet-100"
					:class="{ 'text-white': comparePath('portfolio') }" href="#portfolio">PORTFOLIO</a>
			</ul>
		</div>
		<div class="flex-1 bg-gray-100">
			<div class="overflow-y-scroll h-full scroll-smooth">
				<AboutMe />
				<Experience />
				<Education />
			</div>
		</div>
	</div>
</template>

<style scoped>

</style>
