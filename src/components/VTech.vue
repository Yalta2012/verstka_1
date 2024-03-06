<script setup>
const tech = [
    {
        src: '/php.png',
        alt: 'php.png',
        label: 'PHP'
    },
    {
        src: '/laravel.png',
        alt: 'laravel.png',
        label: 'Laravel'
    },
    {
        src: '/js.png',
        alt: 'js.png',
        label: 'JavaScript'
    }, 
    {
        src: '/nuxt.png',
        alt: 'nuxt.png',
        label: 'Nuxt.js'
    }, 
    {
        src: '/mySQL.png',
        alt: 'mySQL.png',
        label: 'MySQL'
    }, 
    {
        src: '/postgreSQL.png',
        alt: 'postgreSQL.png',
        label: 'PostgreSQL'
    }, {
        src: '/api.png',
        alt: 'api.png',
        label: 'RESTful API'
    }, {
        src: '/gitlab.png',
        alt: 'gitlab.png',
        label: 'GitLab'
    },
]
</script>

<template>
    <section class="tech">
        <div class="container">
            <h2>Технологии</h2>
            <div class="row">
                <div class="col-6 col-lg-3" 
                v-for="(item,index) in tech"
                :key="index">
                    <div class="tech__card">
                        <div class="tech__card-img-wrap">
                            <img :src="item.src" :alt="item.alt">
                            <p>{{item.label}}</p>
                        </div>
                    </div>
                </div>
            
            </div>
        </div>
    </section>
</template>

<style scoped></style>