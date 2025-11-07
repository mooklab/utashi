<script setup>
const scrollToTop = () => {
    window.scrollTo({ top: 0, behavior: 'smooth' });
};
</script>


<template lang="pug">
section.scrollup
    div.conatiner
        img(src="/images/scrollup.svg", @click="scrollToTop")
</template>


<style lang="sass" scoped>
section.scrollup
    position: sticky
    width: 100%
    bottom: 20px
    left: 0
    z-index: 9
    display: grid
    justify-items: end
    margin-top: -50px
    opacity: 0
    img
        cursor: pointer
</style>