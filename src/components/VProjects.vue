<script setup>
const projects = [
    {
        img: {
            src: "/edukesha.png",
            alt: "edukesha.png"
        },
            
        link: {
            href: '#',
            title: 'edukesha'
        },
        description: 'Разработали сервис для проведения онлайн-занятий'
    },
    {
        img: {
            src: "/donationlike.png",
            alt: "donationlike.png"
        },
            
            link: {
            href: '#',
            title: 'DonateLike'
        },
        description: 'Разработали телеграмм-бота для отправки платных реакций'
    },
    {
        img: {
            src: "/gosurguru.png",
            alt: "gosurguru.png"
        },
            
            link: {
            href: '#',
            title: 'go.surgu.ru'
        },
        description: 'Разработали сайт приемной комиссии СурГУ'
    }
]
</script>

<template>
    <section class="projects">
        <div class="container">
            <h2>Проекты</h2>
            <div class="row">
                <div class="col-12 col-sm-6 col-lg-4" 
                v-for="(item,index) in projects"
                :key="index">
                    <div class="projects__card">
                        <img :src="item.img.src" :alt="item.img.alt">
                        <a href="">{{ item.link.title }}</a>
                        <p>{{item.description}} </p>
                    </div>
                </div>
            </div>
        </div>
    </section>
</template>

<style scoped></style>