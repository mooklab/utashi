<template lang="pug">
footer
    div.container
        img(src="/images/logotype.svg", alt="Utashi")
        div.wrap
            div.support
                strong По вопросам сотрудничества и поддержки
                span Email: info@utashi.ru
            span.about Бренд, объединяющий японскую философию совершенства с передовыми технологиями хранения данных. Мы создаём продукты, которые работают безупречно и служат долго.
            span.copyright © Utashi, 2025
</template>

<style lang="sass" scoped>
footer
    margin-top: var(--section-gap)
    margin-bottom: 30px
    +s(m)
        margin-top: 40px
        margin-bottom: 20px

    div.wrap
        display: grid
        align-items: center
        grid-template-columns: 2fr 3fr 1fr
        grid-gap: 60px
        +s(m)
            grid-template-columns: 1fr
            grid-gap: 15px

    div.container
        display: grid
        align-items: center
        grid-template-columns: max-content 1fr
        gap: 60px
        padding: 0 40px
        border-radius: 20px
        height: 100px
        box-shadow: 0 4px 4px 0 rgba(180, 180, 180, 0.25)
        background: #fff
        +s(m)
            align-items: start
            grid-gap: 28px
            padding: 15px
            height: unset

        img
            +s(m)
                height: 49px

        div.support
            display: grid
            grid-gap: 5px
            strong
                font-weight: 600
                line-height: 125%
            span
                font-weight: 400

        span.copyright
            text-align: right
            +s(m)
                text-align: left
                
</style>