<script setup>
import { gsap } from 'gsap';
import { ScrollTrigger } from 'gsap/ScrollTrigger';
import '@/assets/styles/_reset.sass'
import '@/assets/styles/_common.sass'
import 'swiper/css';
import Header from '~/components/Header.vue';
import Main from '~/components/Main.vue';
import About from '~/components/About.vue';
import Philosophy from '~/components/Philosophy.vue';
import Advantages from '~/components/Advantages.vue';
import Products from '~/components/Products.vue';
import Garantee from '~/components/Garantee.vue';
import Footer from '~/components/Footer.vue';
import Scrollup from '~/components/Scrollup.vue';

gsap.registerPlugin(ScrollTrigger)

function animateElements() {
    gsap.utils.toArray('section').forEach(element => {
        gsap.fromTo(element, {
            y: 200,
            opacity: 0,
            filter: 'blur(10px)'
        }, {
            y: 0,
            opacity: 1,
            filter: 'blur(0px)',
            duration: 0.5,
            scrollTrigger: {
                trigger: element,
                start: "top 90%",
                end: "bottom top",
                toggleActions: 'play none none reverse'
                // scrub: true
            }
        })
    })
}

onMounted(() => {
    animateElements()
})
</script>

<template lang="pug">
main
    Header
    Main
    About
    Philosophy
    Advantages
    Products
    Garantee
    Scrollup
Footer
</template>