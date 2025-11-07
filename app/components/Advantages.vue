<template lang="pug">
section.advantages#advantages
    div.container
        div.title
            span Наши преимущества
            div.icon
                div 二
        div.content
            h2 #[b То, что отличает] <br/>нас от других
            div.list
                div
                    img(src="/images/advantages_1.svg")
                    h4 Качество
                    span Многоуровневый контроль качества на каждом этапе производства, от выбора материалов до финальной сборки.
                div
                    img(src="/images/advantages_2.svg")
                    h4 Надёжность
                    span Продукты, созданные для длительной работы в самых требовательных условиях без компромиссов.
                div
                    img(src="/images/advantages_3.svg")
                    h4 Скорость
                    span Оптимизированная производительность для плавной работы с любыми типами данных и приложениями.

</template>

<style lang="sass" scoped>
section.advantages
    margin-top: var(--section-gap)
    margin-bottom: var(--section-gap)
    scroll-margin-top: var(--section-gap)
    +s(m)
        margin-top: 40px
        margin-bottom: 40px
        scroll-margin-top: 40px

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
        display: grid
        grid-gap: 40px
        +s(m)
            grid-gap: 30px

        div.list
            display: grid
            grid-template-columns: repeat(3, 1fr)
            grid-gap: 15px
            +s(m)
                grid-template-columns: 1fr
                grid-gap: 10px
            div
                display: grid
                grid-template-rows: 1fr
                grid-auto-flow: row
                grid-auto-rows: max-content
                align-content: end
                grid-gap: 14px
                border-radius: 20px
                height: 292px
                background: white
                padding: 30px
                +s(m)
                    height: 198px
                    padding: 20px
                    grid-gap: 12px
                span
                    +f(12px, 16px)

</style>