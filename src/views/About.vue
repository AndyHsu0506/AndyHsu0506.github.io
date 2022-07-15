<script setup>
import { ref } from "vue";
import Typing from "@components/Typing.vue";

const step = ref(0);
</script>

<template>
    <div class="h-full w-full px-8 pt-8 sm:px-12 sm:pt-12 lg:px-16 lg:pt-16">
        <Typing
            v-if="step >= 0"
            @done="step++"
            text="About Me"
            class="mb-8 block text-2xl sm:text-3xl lg:text-4xl"
        />

        <Typing v-if="step >= 1" @done="step++" text="As you see, my name is Andy. 
And I'm 16 years old in 2022, also a student, studing at HYSH. 

This summer I went to NTNU CSIE Camp to learn how to code.
Here's what I learned :
" :speed="45" />
<a
    v-if="step >=4"
    class="mt-8 flex items-center text-lg text-gray-500 transition-all hover:text-gray-700 absolute -inset-y-15 left-15"
    href="http://localhost:3000/projects"
    target="_blank"
    >
    <MdiGithub class="mr-1 inline-block" />
    <Typing v-if="step >= 4" @done="step++" text="My Projets" class="italic text-2xl" :speed="80" />
</a>
<img src="https://p3-tt.byteimg.com/origin/pgc-image/768380d0c8c64873a1264091fb6271a9?from=pc.jpg" class="object-cover h-48 w-48 absolute bottom-8 left-0"/>
<Typing v-if="step >= 1" @done="step++" text= "Happy Dog~ " class="absolute bottom-0 left-12"/>
<img src="https://img.ttshow.tw/images/media/uploads/2019/10/04/65a92dc9gy3g7awfnvfvsj20mi0u0ds5.jpg" class="object-cover h-96 w-48 absolute inset-y-12 right-20 "/>
<Typing v-if="step >= 1" @done="step++" text="My idol : G.E.M 鄧紫棋" class="absolute inset-y-10 right-20 "/>
    </div>
</template>
