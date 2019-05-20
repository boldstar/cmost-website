<template>
    <section class="hero container mx-auto">
        <div class="content-column">
            <h1 class="jumbo-title hero-title">Quality Managed Construction</h1>
            <p class="hero-slogan">Whether it's new construction, build out, or renovation, Construction Managers of Southeast Texas are here to help you every step of the way.</p>
            <div class="glide">
                <div data-glide-el="track" class="glide__track">
                    <ul class="glide__slides">
                    <li class="glide__slide"><img src="../../static/img/project1.jpg" alt="contruction image" class="hero-project-img"></li>
                    <li class="glide__slide"><img src="../../static/img/project2.jpg" alt="contruction image" class="hero-project-img"></li>
                    <li class="glide__slide"><img src="../../static/img/project3.jpg" alt="contruction image" class="hero-project-img"></li>
                    <li class="glide__slide"><img src="../../static/img/project4.jpg" alt="contruction image" class="hero-project-img"></li>
                    </ul>
                </div>
            </div>
            <div class="hero-btns">
                <button class="btn btn-main">Learn More</button>
                <div class="divider"></div>
                <button class="btn btn-white">Projects</button>
            </div>
        </div>
    </section>
</template>

<script>
import Glide from '@glidejs/glide'

export default {
    name: 'Hero',
    mounted() {
        new Glide('.glide', {
            perView: 1,
            startAt: 1,
            autoplay: 3000,
            gap: 0,
            type: 'carousel',
            peek: {
                before: 150,
                after: 50
            }
        }).mount()
    }
}
</script>

<style>
    .hero {
        position: relative;
        bottom: -50px;
    }

    .hero-title {
        margin-top: 100px;
    }

    .hero-slogan {
        font-size: 1.5rem;
        text-align: center;
        margin-bottom: 20px;
        padding: 0 35px;
    }

    .glide__slides {
        height: 405px;
    }

    .hero-project-img {
        height: 405px;
        width: 800px;
        object-fit: cover;
        border-radius: 5px;
    }

    .hero-btns {
        display: flex;
        margin: 0 auto;
        margin-top: 20px;
    }
</style>
