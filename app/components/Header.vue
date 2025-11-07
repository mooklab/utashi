<script setup>
import { ref } from 'vue';
const showMenu = ref(false)
function toggleMenu() {
    showMenu.value ? showMenu.value = false : showMenu.value = true
}
</script>


<template lang="pug">
header
    div.container
        div.logotype: img(src="/images/logotype.svg", alt="Utashi")
        menu(:class="{opened: showMenu}")
            a(href="#about") О бренде
            a(href="#advantages") Преимущества
            a(href="#products") Продукты
            a(href="#garantee") Гарантия
        div(@click="toggleMenu()").menu
            img(src="/images/menu.svg", alt="Меню", v-if="!showMenu")
            img(src="/images/cross.svg", alt="Закрыть", v-if="showMenu")
        a(href="mailto:info@utashi.ru").email info@utashi.ru
</template>


<style lang="sass">
header
    height: 100px
    margin-top: 30px
    z-index: 2
    +s(m)
        height: 79px
        margin-top: 20px
        margin-top: 20px

    div.container
        display: grid
        align-content: stretch
        grid-template-columns: max-content 1fr max-content
        grid-gap: 10px

    div.logotype
        display: grid
        align-items: center
        justify-items: center
        border-radius: 20px
        box-shadow: 0 4px 4px 0 rgba(180, 180, 180, 0.25)
        background: white
        width: 143px
        +s(m)
            width: 100px
        img
            +s(m)
                height: 49px

    menu
        display: grid
        grid-auto-flow: column
        grid-auto-columns: 1fr
        border-radius: 20px
        box-shadow: 0 4px 4px 0 rgba(180, 180, 180, 0.25)
        background: white
        +s(m)
            position: absolute
            top: -186px
            left: 0
            width: 100%
            height: 166px
            z-index: -1
            padding: 25px var(--gap)
            grid-auto-columns: max-content
            justify-content: space-between
            transition: all 0.5s
            opacity: 0

        &.opened
            +s(m)
                top: -20px
                opacity: 1

        a
            position: relative
            display: grid
            align-items: center
            justify-items: center
            font-weight: 400
            line-height: 130%
            color: var(--gray)
            +f(12px, 18px)
            transition: color 0.3s
            +s(m)
                align-items: end
            &::after
                content: ''
                position: absolute
                top: calc(50% - 30px)
                right: 0
                display: block
                width: 1px
                height: 60px
                background: var(--gray)
                opacity: 0.2
                +s(m)
                    display: none
            &:hover
                color: var(--red)

    div.menu
        display: none
        pointer-events: none
        +s(m)
            cursor: pointer
            display: grid
            align-items: center
            justify-items: center
            pointer-events: auto

    a.email
        display: grid
        align-items: center
        justify-items: center
        box-shadow: 0 4px 4px 0 rgba(180, 180, 180, 0.25)
        background: white
        padding: 25px
        border-radius: 20px
        font-weight: 600
        font-size: 20px
        line-height: 130%
        color: var(--red)
        +f(12px, 20px)
        +s(m)
            padding: 10px

        &:hover
            color: var(--dark-gray)

</style>