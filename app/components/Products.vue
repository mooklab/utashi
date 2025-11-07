<script setup>
import { ref } from 'vue';
import { Pagination, Navigation } from 'swiper/modules';
import { Swiper, SwiperSlide } from 'swiper/vue';
import ProductCard from './ProductCard.vue';

import SwiperArrow from '~/assets/icons/swiper-arrow.svg'

const prev = ref(null)
const next = ref(null)

</script>

<template lang="pug">
section.products#products
    div.container
        div.title
            span Наши продукты
            div.icon
                div 三
        div.content
            h2 #[b Тщательно продуманные решения] <br/>для различных потребностей
            div.swiper-navigation
                div(ref="prev").arrow: SwiperArrow
                div(ref="next").arrow: SwiperArrow
            swiper(
                ref="swiper"
                :modules="[Pagination, Navigation]",
                :slides-per-view="1",
                :space-between="35",
                :navigation="{ prevEl: prev, nextEl: next }",
                pagination,
                :breakpoints="{640: {slidesPerView: 2}}"
            )
                swiper-slide: ProductCard(title="Utashi Sakura", image="images/card.png")
                swiper-slide: ProductCard(title="Utashi Sakura", image="images/card.png")
                swiper-slide: ProductCard(title="Utashi Sakura", image="images/card.png")
                swiper-slide: ProductCard(title="Utashi Sakura", image="images/card.png")
                swiper-slide: ProductCard(title="Utashi Sakura", image="images/card.png")
                swiper-slide: ProductCard(title="Utashi Sakura", image="images/card.png")
</template>

<style lang="sass" scoped>
section.products
    margin-top: var(--section-gap)
    margin-bottom: var(--section-gap)
    scroll-margin-top: 240px
    +s(m)
        margin-top: 40px
        margin-bottom: 50px
    div.title
        display: grid
        align-items: center
        justify-content: space-between
        grid-template-columns: repeat(2, max-content)
        border-bottom: 1px solid var(--gray)
        padding-bottom: 20px
        margin-bottom: 40px
        +s(m)
            padding-bottom: 15px
            margin-bottom: 20px
        span
            font-weight: 300
            line-height: 130%
            letter-spacing: 0.01em
            text-transform: uppercase
            color: var(--gray)
            +f(14px, 20px)
        div.icon
            div
                color: var(--red)
                +f(20px, 32px)

    div.content
        position: relative
        display: grid
        grid-template-columns: 1fr max-content
        grid-gap: 40px
        align-items: end
        +s(m)
            grid-template-columns: 1fr

    div.swiper
        min-width: 0
        width: 100%
        grid-column: 2 span
        +s(m)
            grid-column: 1 span

    div.swiper-navigation
        display: grid
        grid-auto-flow: column
        grid-auto-columns: max-content
        grid-gap: 5px
        user-select: none
        +s(m)
            display: none
        div.arrow
            cursor: pointer
            display: grid
            align-items: center
            justify-items: center
            border: 1px solid var(--gray)
            border-radius: 6px
            width: 28px
            height: 28px
            transition: all 0.3s

            &:first-child
                transform: rotate(180deg)

            &:hover
                background: var(--red)
                border: 1px solid var(--red)

                :deep(svg)
                    path
                        stroke: white


            &.swiper-button-disabled
                opacity: 0.2
                pointer-events: none


    :deep(div.swiper-pagination)
        justify-content: center
        justify-items: center
        margin-top: 32px
</style>