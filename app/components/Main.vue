<script setup>
import { Pagination } from 'swiper/modules';
import { Swiper, SwiperSlide } from 'swiper/vue';
import { main } from '~/assets/data';
</script>

<template lang="pug">
section.main
    div.container
        swiper(
            :modules="[Pagination]",
            :auto-height="true",
            pagination
        )
            swiper-slide(v-for="(slide, index) in main", :key="index")
                div.image
                    img(:src="slide.image", :alt="slide.title")
                div.text
                    h1 {{ slide.title }}
                    span {{ slide.text }}
                    button Изучить продукты

    img(src="/images/ball.png").ball.first
    img(src="/images/ball.png").ball.second
</template>


<style lang="sass" scoped>
section.main
    margin-bottom: calc(var(--section-gap)*2)
    margin-top: calc(var(--section-gap)*2)
    +s(m)
        margin-top: 70px
        margin-bottom: 70px
    div.swiper-slide
        display: grid
        grid-template-columns: 1fr
        align-items: center
        grid-gap: 60px
        +s(m)
            justify-items: center
            grid-gap: 30px
    div.image
        position: absolute
        width: 50%
        height: 100%
        display: grid
        align-items: center
        justify-items: center
        +s(m)
            width: 100%
            height: 100%
            position: relative
            height: 300px
        img
            position: absolute
            max-width: 100%
            max-height: 100%
            object-fit: contain
    div.text
        position: relative
        display: grid
        justify-items: start
        grid-gap: 40px
        max-width: 460px
        width: 50%
        margin-bottom: 80px
        left: 50%
        +s(m)
            left: 0
            width: 100%
            text-align: center
            justify-items: center
            justify-content: center
            grid-gap: 30px
            margin-bottom: 40px
        span
            display: block
            font-weight: 300
            line-height: 130%
            color: var(--gray)
            +f(16px, 20px)
        button
            cursor: pointer
            border-radius: 10px
            height: 45px
            background: var(--red)
            font-weight: 500
            font-size: 14px
            line-height: 130%
            text-transform: uppercase
            color: white
            padding: 0 22px
            transition: all 0.5s
            +s(m)
                width: 100%

            &:hover
                filter: brightness(90%)

    :deep(div.swiper-pagination)
        position: absolute
        bottom: 0
        left: 50%
        +s(m)
            transform: translateX(-50%)
        
    img.ball.first
        grid-column: full
        position: absolute
        top: -215px
        left: -177px
        filter: blur(8px)
    img.ball.second
        grid-column: full
        position: absolute
        width: 271px
        height: 271px
        top: 28px
        right: 62px
        filter: blur(8px)
</style>