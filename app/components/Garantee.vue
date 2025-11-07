<template lang="pug">
section.garantee#garantee
    div.container
        img(src="/images/five.svg", alt="Гарантия качества")
        div.text
            span Гарантия качества
            h2 Наша уверенность в продуктах — #[b ваша уверенность в выборе]
            p Каждый продукт Utashi Digital проходит тщательное тестирование и сопровождается расширенной гарантией 5 лет. Мы настолько уверены в качестве нашей продукции, что готовы нести ответственность за её надёжность все эти годы.
</template>

<style lang="sass" scoped>
section.garantee
    margin-top: var(--section-gap)
    margin-bottom: var(--section-gap)
    +s(m)
        margin-top: 40px
        margin-bottom: 40px

    div.container
        display: grid
        justify-items: center
        text-align: center
        grid-gap: 62px
        border-radius: 20px
        padding-top: 100px
        padding-bottom: 100px
        background: white
        +s(m)
            padding-top: 40px
            padding-bottom: 40px
            grid-gap: 40px

        img
            +s(m)
                height: 160px

        div.text
            display: grid
            max-width: 800px
            span
                font-weight: 300
                line-height: 130%
                letter-spacing: 0.01em
                text-transform: uppercase
                margin-bottom: 18px
                +f(14px, 20px)
            h2
                margin-bottom: 32px
                +s(m)
                    margin-bottom: 24px
            p
                font-weight: 300
                line-height: 130%
</style>