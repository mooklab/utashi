<script setup>
import { ref } from 'vue';

const props = defineProps({
    title: String,
    image: String
})

const showSpecs = ref(false)

function toggleList() {
    showSpecs.value ? showSpecs.value = false : showSpecs.value = true
}
</script>

<template lang="pug">
div.product
    img(:src="props.image", :alt="props.title").preview
    div.description
        h4: b {{ props.title }}
        span Карта памяти, сочетающая элегантный дизайн с выдающейся производительностью для фотографов и видеографов.
    div.specs
        strong Надёжность для профессионального использования
        ul
            li
                div 一
                span Используются качественные протестированные good die чипы памяти, обеспечивающие до 3000 циклов записи/стирания
            li
                div 二
                span Идеально подходят для видеорегистраторов и систем видеонаблюдения
            li
                div 三
                span Рабочий диапазон температур: 0°C до +70°C
            li
                div 四
                span Диапазон температур хранения: -25°C до +85°C
            li
                div 五
                span Защита от подделок: упаковка имеет рельефное тиснение
            div(:class="{ opened : showSpecs }").additional 
                div.overflow
                    div.wrap
                        li
                            div 一
                            span Используются качественные протестированные good die чипы памяти, обеспечивающие до 3000 циклов записи/стирания
                        li
                            div 二
                            span Идеально подходят для видеорегистраторов и систем видеонаблюдения
                        li
                            div 三
                            span Рабочий диапазон температур: 0°C до +70°C
                        li
                            div 四
                            span Диапазон температур хранения: -25°C до +85°C
                        li
                            div 五
                            span Защита от подделок: упаковка имеет рельефное тиснение
    a(@click="toggleList()").button 
        span(v-if="!showSpecs") Технические характеристики
        span(v-if="showSpecs") Скрыть
        img(src="/images/product_arrow.svg", :class="{opened: showSpecs}")
</template>

<style lang="sass" scoped>
div.product
    display: grid
    grid-gap: 40px
    background: white
    border-radius: 20px
    padding: 40px
    +s(m)
        grid-gap: 20px
        padding: 20px 15px
        border-radius: 8px

    img.preview
        max-height: 400px
        width: 100%
        object-fit: contain
        +s(m)
            max-height: 160px

    div.description
        display: grid
        grid-gap: 20px
        +s(m)
            grid-gap: 10px

    div.specs
        display: grid
        grid-gap: 24px
        +s(m)
            grid-gap: 12px

        strong
            font-weight: 600
            line-height: 130%
            +f(14px, 18px)

        li
            display: grid
            grid-template-columns: max-content 1fr
            grid-gap: 20px
            border-top: 1px solid #5D6D7E20
            padding-bottom: 16px
            padding-top: 20px
            +s(m)
                padding-top: 8px
                padding-bottom: 8px
                grid-gap: 8px

            div
                font-weight: 600
                color: var(--red)
                +f(12px, 16px)

            span
                font-weight: 300
                line-height: 130%
                color: var(--gray)

            &:first-child
                padding-top: unset
                border: unset

            &:last-child
                padding-bottom: unset

    div.additional
        display: grid
        grid-template-rows: 0fr
        transition: all 0.3s
        div.overflow
            overflow: hidden
        &.opened
            grid-template-rows: 1fr

        li:first-child
            border-top: 1px solid #5D6D7E20
            padding-top: 20px
            +s(m)
                padding-top: 8px

    a.button
        display: grid
        align-items: center
        grid-template-columns: 1fr max-content
        border: 1px solid var(--red)
        border-radius: 10px
        height: 55px
        padding: 16px
        +s(m)
            height: 40px
            padding: 0 10px
            border-radius: 4px
        span
            font-weight: 600
            color: var(--red)
        img
            transition: all 0.3s
            &.opened
                transform: rotate(180deg)
</style>