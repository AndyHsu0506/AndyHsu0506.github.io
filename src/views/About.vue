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
And I'm 16 years old in 2022, also a student, studing at HYSH." />
<img src="https://p3-tt.byteimg.com/origin/pgc-image/768380d0c8c64873a1264091fb6271a9?from=pc.jpg" class="object-cover h-48 w-48"/>
<img src="https://img.ttshow.tw/images/media/uploads/2019/10/04/65a92dc9gy3g7awfnvfvsj20mi0u0ds5.jpg" class="object-cover h-96 w-48"/>
    </div>
</template>
