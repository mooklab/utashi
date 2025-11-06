<template lang="pug">
section.philosophy
    div.container

        div.title
            span Философия совершенства
            h2 #[b Три принципа] <br/>нашего подхода

        div.list
            div
                span 一
                p Простота в использовании
                img(src="/images/ball.png")
            div
                span 二
                p Надёжность в работе
                img(src="/images/ball.png")
            div
                span 三
                p Элегантность в форме
                img(src="/images/ball.png")

        div.final Совершенство в деталях
</template>


<style lang="sass" scoped>
section.philosophy
    text-align: center
    padding-top: var(--section-gap)
    padding-bottom: var(--section-gap)
    background: white
    +s(m)
        padding-top: 45px
        padding-bottom: 45px

    div.container
        display: grid
        justify-content: center
        grid-gap: 60px
        +s(m)
            grid-gap: 30px

    div.title
        display: grid
        grid-gap: 20px
        span
            font-weight: 300
            line-height: 130%
            letter-spacing: 0.01em
            text-transform: uppercase
            text-align: center
            color: var(--gray)
            +f(14px, 20px)

    div.list
        display: grid
        grid-template-columns: repeat(3, max-content)
        grid-gap: 50px
        +s(m)
            grid-gap: 10px
            grid-template-columns: repeat(2, max-content)
            justify-items: center

        div
            position: relative
            display: grid
            align-content: center
            justify-items: center
            grid-gap: 30px
            width: 338px
            height: 338px
            +s(l)
                width: 240px
                height: 240px
            +s(m)
                width: 164px
                height: 164px
                grid-gap: 20px
            &:nth-child(2)
                width: 368px
                height: 368px
                +s(l)
                    width: 240px
                    height: 240px
                +s(m)
                    width: 164px
                    height: 164px
            &:nth-child(3)
                +s(m)
                    grid-column: 2 span
                    justify-content: center
                    justify-items: center

            span
                display: block
                font-weight: 300
                line-height: 130%
                color: var(--red)
                +f(24px, 48px)

            p
                display: block
                font-weight: 300
                line-height: 130%
                text-align: center
                max-width: 140px
                +f(12px, 20px)
                +s(m)
                    max-width: 100px

            img
                position: absolute
                top: 0
                left: 0
                width: 100%
                height: 100%
                object-fit: contain
                filter: blur(4px)
    div.final
        font-style: italic
        font-weight: 300
        text-align: center
        color: var(--gray)
        +f(16px, 32px)
        &:before
            content: ''
            position: relative
            display: block
            width: 1px
            height: 56px
            background: var(--red)
            left: 50%
            margin-bottom: 30px
</style>