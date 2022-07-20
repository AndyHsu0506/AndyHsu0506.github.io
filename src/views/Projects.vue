<script setup>
import { ref, watch } from "vue";
import { random_text } from "@/utils";
import Typing from "@components/Typing.vue";
import Project from "@components/Project.vue";
import Fade from "../components/Fade.vue";

const projects = [
    {
        name: "製作個人網站",
        description: "第一次自己編輯的網站~我覺得還有超大的進步空間(那是肯定的吧哈哈哈)",
        image: "I'm sorry, there's no image.",
        link: "https://docs.google.com/presentation/d/1Qjg_cUy1tVS9u490QG6cQT32o-vcEcCnlsdjRS1G908/edit#slide=id.g8f4bd20341_0_1",

    },
    {
        name: "AiGoBang",
        description: "和大家一起寫的aigobang！應該還是有很多bug，但目前能力有限，之後學到更多東西後會回頭再次審視" + random_text(64),
        image: "I'm sorry, there's no image.",
        link: "https://docs.google.com/presentation/d/16WDCpUAY7AumZ6vjNC-fkRMxm9zPkQKsYVvyrPEenM0/edit#slide=id.g8f4bd20341_0_1",

    },
    {
        name: "Linux",
        description: "在營隊中學到了不少基本指令，雖然是基礎，但知識又加廣了!而且我真的覺得超酷" + random_text(64),
        image: "I'm sorry, there's no image.",
        link: "https://docs.google.com/presentation/d/16WDCpUAY7AumZ6vjNC-fkRMxm9zPkQKsYVvyrPEenM0/edit#slide=id.g8f4bd20341_0_1",
        
    },
    {
        name: "tablecloth",
        description: "很開心有了屬於自己的桌布！" + random_text(64),
        image: "I'm sorry, there's no image.",
        link: "https://docs.google.com/presentation/d/16WDCpUAY7AumZ6vjNC-fkRMxm9zPkQKsYVvyrPEenM0/edit#slide=id.g8f4bd20341_0_1",

    },
];

const step = ref(0);
let interval = -1;

watch(step, () => {
    if (step.value > 0 && interval === -1) {
        interval = window.setInterval(() => {
            step.value++;
            if (step.value >= projects.length) {
                window.clearInterval(interval);
            }
        }, 200);
    }
});
</script>
<template>
    <div class="h-full w-full px-8 pt-16 sm:px-12 sm:pt-20 lg:px-16 lg:pt-24">
        <Typing
            v-if="step >= 0"
            @done="step++"
            text="My Projects"
            class="block text-2xl sm:text-3xl lg:text-4xl"
        />
        <div class="py-2">
            <div v-for="(project, index) in projects">
                <Fade>
                    <Project
                        v-if="step >= index + 1"
                        :key="index"
                        class="my-2 w-full rounded-md bg-white bg-opacity-50 p-4 shadow-md shadow-indigo-200"
                        :name="project.name"
                        :description="project.description"
                        :image="project.image"
                        :link="project.link"
                        :tags="project.tags"
                    />
                </Fade>
            </div>
        </div>
    </div>
</template>
