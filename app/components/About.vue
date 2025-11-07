<template lang="pug">
section.about#about
    div.container
        div.title
            span О бренде
            div.icon
                div 一
        div.content
            h2 #[b Технологии] в духе японской философии совершенства
            img(src="/images/card.png", alt="")
            div
                h3 #[b Utashi Digital] — это воплощение японской философии «Кайдзен» (постоянное совершенствование) в мире технологий.
                span Мы верим, что каждая деталь имеет значение. <br/>Наш подход сочетает внимательность к мелочам, стремление к простоте и бескомпромиссное качество.
</template>

<style lang="sass" scoped>
section.about
    margin-top: calc(var(--section-gap)*2)
    margin-bottom: var(--section-gap)
    scroll-margin-top: var(--section-gap)
    +s(m)
        margin-top: 70px
        margin-bottom: 40px
        scroll-margin-top: 70px
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
        grid-template-columns: repeat(3, 1fr)
        grid-gap: var(--gap)
        +s(m)
            grid-template-columns: 1fr
        img
            max-height: 480px
            width: 100%
            object-fit: contain
            +s(m)
                max-height: 320px
        div
            display: grid
            grid-gap: 24px
            align-self: end
            span
                display: block
                border-left: 1px solid var(--red)
                padding-left: 20px
                color: var(--gray)
                +f(12px, 16px)
</style>