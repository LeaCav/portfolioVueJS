<script setup>
import {ref} from 'vue';
import Modal '@/components/Modal.vue';



const creation = ref ([
    {
        title: 'Mon Curriculum Vitae',
        img: '../assets/img/icons8-fermer-la-fenêtre-100.png',
        date: 30/1/2024,
        usedTech: 'HTML5 / CSS3',
        link: 'https://github.com/LeaCav/cv-lea-cavalli/tree/main>ici</a></strong'
    },
    {
        title: 'Cahier des charges',
        img: '../assets/img/icons8-fermer-la-fenêtre-100.png',
        date: 15/2/2024,
        usedTech: 'Google doc / Inkscape / Paint 3D / Adobe color',
        link: '../views/Error.vue',
    },
    {
        title: 'Travail avec JavaScript' ,
        img: '../assets/img/icons8-fermer-la-fenêtre-100.png',
        date: 26/2/2024,
        usedTech: 'HTML 5 / CSS 3 / JavaScript',
        link: 'https://github.com/LeaCav/dynamiser-un-espace-commentaire' ,
    },
    {
        title: 'Mon site de tests',
        img: '../assets/img/icons8-fermer-la-fenêtre-100.png',
        date: 27/2/2024,
        usedTech: 'HTML 5 / CSS 3 / JavaScript / Inkscape / Adobe color',
        link: 'https://github.com/LeaCav/mon-site-de-tests',
    },
]);

const openModal = (project) => {
    const modalData = {
        title: project.title,
        img: project.img,
        date: project.date,
        usedTech: project.usedTech,
        link: project.link,
    };
    Modal.open(modalData);
};

</script>

<template>
        <h2>Mes projets</h2>
        <div id="divProjet">
            <button @click="openModal(creation[0])" type="button">
                <section >
                    <h3>Mon Curriculum Vitae</h3>
                    <img src="../assets/img/cv1.png" alt="Curriculum Vitae" title="Curriculum Vitae">
                </section>
            </button>

            <button @click="openModal(creation[1])" type="button">
                <section id = openModal2>
                    <h3>Cahier des charges</h3>
                    <img src="../assets/img/cahier-des-charges.png" alt="Cahier des charges" title="Cahier des charges">
                </section>
            </button>

            <button @click="openModal(creation[2])" type="button">
                <section id = openModal3>
                    <h3>Travail avec JavaScript</h3>
                    <img src="../assets/img/js.png" alt="Dynamiser un espace commentaire" title="Dynamiser un espace commentaire">
                </section>
            </button>

            <button @click="openModal(creation[3])" type="button">
                <section id = openModal4>
                    <h3>Mon site de tests</h3>
                    <img src="../assets/img/logo.jpg" alt="Mon site de tests" title="Mon site de tests">
                </section>
            </button>
        </div>
</template>

<style scoped>
#divProjet{
    margin-top:30px ;
    margin-bottom: 100px;
    display: flex;
}
button{
    background-color: #ffff;
    border:none;
}

section{
    height: 350px;
    display: flex;
    flex-direction: column;
}
section:hover{
    box-shadow: 0.5rem 0.5rem 0.5rem  #33402B;
}
section:active{
    box-shadow: 0.5rem 0.5rem 0.5rem  #618C6C;
}
h2{
    Margin-top: 100px;
    width: 400px;
    color: #F2B366;
    font-size: 1.4rem;
    background: rgb(51,64,43);
    background: radial-gradient(circle, rgba(51,64,43,1) 0%, rgba(255,255,255,1) 100%);
}
h3{
    font-size: 1.2rem;
}
img{
    width: 300px;
    margin: 10px;
    cursor:pointer;
}
</style>

